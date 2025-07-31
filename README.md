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
     def move_snake(snake,direction):
        head=snake[-1]
        if direction=='up':
            new_head=[head[0],head[1]-1]
        elif direction=='down':
            new_head=[head[0],head[1]+1]
        elif direction=='left':
            new_head=[head[0]-1,head[1]]
        elif direction=='right':
            new_head=[head[0]+1,head[1]]
        else:
            print("Invalid direction,use left/right/down/up.")
            return snake,False
