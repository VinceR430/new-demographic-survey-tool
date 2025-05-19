name = " "
sex = " "
male_amount = 0
female_amount = 0
male_totalage = 0
female_totalage = 0
male_avgage = float()
female_avgage = float()
list_people = []

while True:
    name = input("Enter name or press enter to exit list: ")
    if name == "":
        break  # Moved this line to the correct position
    sex = input("Enter sex (Male/Female) here: ")  # Moved this line outside the break condition
    age = input("Enter age (18-65) here: ")

    try:
        age = float(age)
    except ValueError:
        print("Invalid input of age. Please enter a number")
        continue  # Added continue to skip to the next iteration

    if sex == "Male":
        if 18 <= age <= 65:  # Removed unnecessary int() conversion
            male_amount += 1
            male_totalage += age
        else:
            print("Selected age was outside of the parameters. Please reenter information again.")
    elif sex == "Female":
        if 18 <= age <= 65:  # Removed unnecessary int() conversion
            female_amount += 1
            female_totalage += age
        else:
            print("Selected age was outside of the parameters. Please reenter information again.")
    else:
        print("Selected Sex was input incorrectly. Loop will start over.")

    list_people.append(name)
    list_people.append(sex)
    list_people.append(age)

print("The list has been exited. Count and average ages will be computed.")


try:
    female_avgage = (female_totalage // female_amount)
    print("The female count is:")
    print(female_amount)
    print("The average female age:")
    print(female_avgage)
except:
    print("There is no data for females")

try:
    male_avgage = (male_totalage // male_amount)
    print("The male count is:")
    print(male_amount)
    print("The average male age:")
    print(male_avgage)
except:
    print("There is no data for males")
