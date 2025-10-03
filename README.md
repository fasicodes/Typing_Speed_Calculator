from time import  *
import random

def error(paragraph,user_text ):
    "chick the error in text"
    error = 0
    for i in range(len(paragraph)):
        try:
            if paragraph[i] != user_text[i] :
              error += 1 
        except :
           error = error + 1  
    return error 

def accuracy(usertext,error):
    if len(usertext)==0 :
        return 0
    accuracy_formula  = (len(usertext) - error)/len(usertext)*100
    accuracy_r = round(accuracy_formula,2)
    return accuracy_r


def speed(time_s , time_f,user_text) :
    "chick the speed of user "
    words = user_text.split() # convert the letter into words
    actual_time = time_f - time_s # measure the toatl time
    actual_time_r = round(actual_time,2)
    minutes = actual_time_r / 60 #converts the second into minutes
    if minutes == 0 :
        return 0
    minutes_r = round(minutes,2)
    speed = (len(words) / minutes_r) 
    return round(speed,2)
    

           
text = [
    "Discipline is the bridge between goals and achievements. Without it, talent is wasted and opportunities are lost. A steady routine, even in small actions, builds the foundation of success.",

    "Technology makes life faster and easier, yet it silently steals attention and focus. True progress comes when we control our devices instead of being controlled by them.",

    "Time is the only resource that cannot be regained. Each moment matters, and wise people treat every second as an investment in their future."
]

text_random = random.choice(text)
print(text)
time1 = time()
userinput = input("Enter the text:  ")
time2 = time()
error_in_text = error(text,userinput)
speed_of_user = speed(time1,time2,userinput)
accuracy_of_user = accuracy(userinput,error_in_text)
print(f"The error in text = {error_in_text}")
print(f"The speed of user is {speed_of_user} words / minute")
print(f"The accuracy of user is {accuracy_of_user}%")





print(f"The accuracy of user is {accuracy_of_user}%")

