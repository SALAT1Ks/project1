import keyboard
import os
from tkinter import *
from pathlib import Path
import pyautogui as pg
from time import sleep

root = Tk()
def zapis():
    sleep(1)
    recorded_events = keyboard.record("esc")
    os.startfile(r'C:\oh\wors.txt')
    sleep(2)
    keyboard.play(recorded_events)


def proizvodstvo():
    words = [w for w in Path('C:\oh\wors.txt').read_text(encoding="utf-8").replace("\n", " ")]
    sleep(3)
    for i in range(len(words)):
        pg.keyDown(words[i])
        sleep(1)
        pg.keyUp(words[i])

def proizviRUS():
    words = [w for w in Path('C:\oh\wors.txt').read_text(encoding="utf-8").replace("\n", " ")]
    sleep(5)
    for i in range(len(words)):
        i = i


root.title('Скрипт')
root.geometry('500x500')

button1 = Button(root, text='запись', font=40, command=zapis)
button1.pack(side=BOTTOM, pady=40)

button2 = Button(root, text='Начать 1', font=40, command=proizvodstvo)
button2.pack(side=BOTTOM, pady=40)

button3 = Button(root, text='Начать 2(RUS)', font=40, command=proizviRUS)
button3.pack(side=BOTTOM, pady=40)

root.mainloop()
with open("C:\\Users\\oppoe\\Downloads\\27-168a (1).txt") as f:
    n, k = map(int, (f.readline()).split())
    sp = [int(x) for x in f]
    maxxx = max(sp)
    maxx = max(sp)
    if sp.index(maxx) + k > len(sp):
        maxx = max(x for x in sp if x != max(sp))

    maxx2 = max(sp[sp.index(maxx)+k+1:])
    if sp.index(maxx2) + k > len(sp[sp.index(maxx2):]):
        maxx2 = max(x for x in sp if x != max(sp[sp.index(maxx2):]))
    maxx3 =max(sp[sp.index(maxx2):])

print((maxx*maxx2*maxx3)%(10**6+1))
print(sp.index(maxx))
print(sp.index(maxx2))
print(sp)
print(sp[sp.index(maxx)+k+1:])
print(sp[sp.index(maxx2):])
print(maxx3)