```python

#copy all of this into: https://trinket.io/embed/python3/a5bd54189b
import random
import time
import tkinter.font as font
import tkinter as tk
from PIL import Image, ImageTk


while True:    
    print("Do you want to use:")
    time.sleep(1)
    print(" 1. The insult generator")
    time.sleep(1)
    print(" 2. The calculator")
    time.sleep(1)
    print(" 3. Dino Game!")
    option = int(input(""))
    if option == 1:
        print("🤬 Welcome to the random insult generator! 🤬")
        while True:
            while True:
                print("Do you want a random insult? (Y/N)")
                answer = input("")
                if answer == "Y" or answer == "y":
                    break
                elif answer == "N" or answer == "n":
                    print("Why...")
                    time.sleep(2)
                    print("Not?...")
                    time.sleep(2)
                    print("oh well, we will give you one anyway.")
                    break
                else:
                    print("ERR. \n Something went wrong.")

            time.sleep(2)
            print("okay...")
            time.sleep(2)
            print("here it comes...")
            time.sleep(2)
            num = random.randint(0, 15)
            if num == 0:
                print("You are a clanker!!!!! \n (credit to Rhine Shome)")
            if num == 1:
                print("You are dumb!!!! \n (credit to Jeremy)")
            if num == 2:
                print("You are a pig!!!! \n (credit to Oshi)")
            if num == 3:
                print("You are a banana-head!!! \n (credit to Anonymouse)")
            if num == 4:
                print("You're forehead is massive!!! \n (credit to Favour)")
            if num == 5:
                print("You are a cotton-headed ninny-muggins!!! \n (credit to Joshua C)")
            if num == 6:
                print("You make me feel smart when i am around you!! \n (credit to Sam)")
                time.sleep(1)
                print("(the ancient one)")
                time.sleep(1)
                print("(X2)")
                time.sleep(1)
                print("(X3)")
                time.sleep(1)
                print("(X1,000,000,000,000)")
                time.sleep(1)
                print("(X∞)")
            if num == 7:
                print("You Prince Of Wales!!! \n (credit to Adrian)")
            if num == 8:
                print("You worm!!! \n (credit to Joshua B)")
            if num == 9:
                print("You seat stealer!!! \n (credit to Carla)")
            if num == 10:
                print("You're so clumsy that you lost your keys")
                time.sleep(1)
                print("From your keyboard!!\n (credit to Zephyr)")
                time.sleep(1)
                print("(the creator)")
            if num == 11:
                print("You egg!!! \n (credit to Shakespeare)")
            if num == 12:
                print("You lower the IQ of the street when you open your mouth!! \n (credit to Matt)")
            if num == 13:
                print("You diddy-blud \n (credit to Sam (the young one))")
            if num == 14:
                print("I literally could not give poo about this \n (credit to Cohen)")
            if num == 15:
                print("You are an underpaid lawyer!!! \n (credit to Alex)")

            yesorno = 0
            while True:
                goagain = input("do you want to go again? (Y/N)")
                if goagain == "N" or goagain == "n":
                    print("Goodbye, you #$@!")
                    yesorno = 1
                    break
                if goagain == "Y" or goagain == "y":
                    print("Yaay!")
                    break
                elif goagain == "actually id rather be prince of scotland" and num == 7:
                    print("Stop changing the (royal) subject!!!! \n (copyrighted by Joshua B)")
                else:
                    print("ERR. \n Something went wrong.")

            if yesorno == 0:
                print("processing")
                time.sleep(0.1)
                print("processing.")
                time.sleep(0.1)
                print("processing..")
                time.sleep(0.1)
                print("processing...")
                time.sleep(0.1)
                print("processing")
                time.sleep(0.1)
                print("processing.")
                time.sleep(0.1)
            else:
                break
    elif option == 2:
        while True:
            print("🖩Welcome to the calculator!!🖩")
            while True:
                symbol = int(input("Do you want to \n 1. Add\n 2. Divide\n 3. Multiply\n 4. Subtract\n"))
                if symbol == 1:
                     num1 = float(input("Give me one number"))
                     num2 = float(input("Give me another number"))
                     answ = num1+num2
                     print(f'{num1}➕{num2} = {answ}')
                if symbol == 2:
                     num1 = float(input("Give me one number"))
                     num2 = float(input("Give me another number"))
                     answ = num1/num2
                     print(f'{num1}➗{num2} = {answ}')
                if symbol == 3:
                     num1 = float(input("Give me one number"))
                     num2 = float(input("Give me another number"))
                     answ = num1*num2
                     print(f'{num1}✖️{num2} = {answ}')
                if symbol == 4:
                     num1 = float(input("Give me one number"))
                     num2 = float(input("Give me another number"))
                     answ = num1-num2
                     print(f'{num1}➖{num2} = {answ}')
    elif option == 3:
        print("processing")
        time.sleep(0.1)
        print("processing.")
        time.sleep(0.1)
        print("processing..")
        time.sleep(0.1)
        print("processing...")
        time.sleep(0.1)
        print("processing")
        time.sleep(0.1)
        print("processing.")
        time.sleep(0.1)
        
        WIDTH = 800
        HEIGHT = 300
        GROUND_Y = 250

        root = tk.Tk()
        root.title("Dino Game")

        canvas = tk.Canvas(root, width=WIDTH, height=HEIGHT, bg="white")
        canvas.pack()
        canvas.create_line(0, GROUND_Y, WIDTH, GROUND_Y, width=2)
        dino_image = Image.open(r"C:\Users\Neil Carrington\Downloads\dino\dino.png")
        dino_image = dino_image.resize((50, 50))
        dino_photo = ImageTk.PhotoImage(dino_image)
        dino = canvas.create_image(70, 210, image=dino_photo)
        velocity_y = 0
        gravity = 1
        jumping = False
        # Obstacle
        obstacle = canvas.create_rectangle(
            700, 220, 740, 250,
            fill="red"
        )

        game_over = False

        def jump(event):
            global velocity_y, jumping

            if not jumping:
                velocity_y = -15
                jumping = True

        root.bind("<space>", jump)

        def get_dino_bbox():
            x, y = canvas.coords(dino)

            return (
                x - 25,
                y - 25,
                x + 25,
                y + 25
            )
        def game_loop():
            global velocity_y, jumping, game_over

            if game_over:
                return
            # Apply gravity
        canvas.move(dino, 0, velocity_y)
        velocity_y += gravity

        # Dino position
        x1, y1, x2, y2 = get_dino_bbox()

        # Ground collision
        if y2 >= GROUND_Y:
            canvas.move(dino, 0, GROUND_Y - y2)
            velocity_y = 0
            jumping = False
            # Move obstacle
        canvas.move(obstacle, -10, 0)

        obs = canvas.coords(obstacle)

        # Reset obstacle
        if obs[2] < 0:
            canvas.move(obstacle, WIDTH, 0)
            # Collision detection
        overlap = not (
            x2 < obs[0] or
            x1 > obs[2] or
            y2 < obs[1] or
            y1 > obs[3]
        )

        if overlap:
            game_over = True

            canvas.create_text(
                WIDTH // 2,
                HEIGHT // 2,
                text="GAME OVER",
                font=("Arial", 30),
                fill="black"
            )

        root.after(30, game_loop)

        game_loop()

        root.mainloop()
    else:
        print(f'I dont know what "{option}" means')
    break

    
        


```
