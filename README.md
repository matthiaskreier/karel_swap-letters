# karel_swap-letters
From SuperKarel in CodeHS to swap an image of balls like a mirror

Not sophisticated, but it works:

``` py
def swap():
    height = 0
    for k in range(50):
        width = 0
        linie  = 0
        for i in range(100):
            if balls_present():
                linie += 2 ** i
                take_ball()
            if front_is_clear():
                width += 1
                move()
            else:
                break
        back(width)
        turn_around()
        for i in range(width, 0, -1):
            if linie / (2 ** i) > 0:
                put_ball()
            linie = linie % (2 ** i)
            move()
        back(width)
        if right_is_clear():
            turn_right()
            height += 1
            move()
            turn_right()
        else:
            turn_left()
            for i in range(height):
                move()
            turn_left()
            break

def back(y):
    turn_around()
    for x in range(y):
        move()

swap()
```
