# gaming
import random
width=10
height=10

def print_board(snake,food):
    for y in range(height):
        for x in range(width):
            if [x,y]==food:
                print('F',end='')
            elif [x,y] in snake:
                print('S',end='')
            else:
                print('.',end='')
        print()
    print()
