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
#wall conditions
        if new_head[0]<0 or new_head[0]>=width or new_head[1]<0 or new_head[1]>=height:
            return snake,'wall'
#self collide conditions
        if new_head in snake:
            return snake,'self'
        snake.append(new_head)
        return snake,new_head
def place_food(snake):
    while True:
        x=random.randint(0,width-1)
        y=random.randint(0,height-1)
        if [x,y] not in snake:
            return[x,y]
        
