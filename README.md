PyAutoEasy
=========

PyAutoEasy is a utility wrapper around the famous [PyAutoGUI](https://pypi.org/project/PyAutoGUI/), a cross-platform GUI automation tool to replace your boooring repetitive tasks. 

When PyAutoGUI offers powerful ways to control keyboard and mouse movements, PyAutoEasy makes it super easy to grab the cursor positions on the screen and give meaningful names to them and generate the boilerplate program which we can easily modify to suit our needs. 


How to install
============

`pip install pyautoeasy`


Example Usage
=============

Step 1 : Generate initial code after grabbing the required locations in the screen
--------------------------
1. Open a terminal / command prompt and run `pyautoeasy`
2. Move your cursor to the desired location and press `alt+r` in the keyboard to record the coordinates of a point in the screen.
3. This opens up a dialog box, Now give a name to this point and click OK.
4. Repeat the above 2 steps for all the cursor locations that you want to grab.
5. Press `alt+s` to generate your initial automation script. (`sample.py`)

Step 2 : Modify the sample script to suit your needs.
--------------------------
Lets say you wanna create a login automation. Follow step 1 to record all desired locations in the screen like email, password fields, submit button etc.
The generated sample program would look something like this. 
```
from pyautoeasy import ScreenPoint

email_field = ScreenPoint(pos=(952, 309))
email_field.click_here()

password_field = ScreenPoint(pos=(934, 438))
password_field.click_here()

submit_button = ScreenPoint(pos=(1127, 597))
submit_button.click_here()
```
Now you can take above generated file and easily modify it to something like this. Super easy and intuitive!

```
from pyautoeasy import ScreenPoint

email_field = ScreenPoint(pos=(952, 309))
email_field.click_here()
email_field.type_here("mytestemail@gmail.com")

password_field = ScreenPoint(pos=(934, 438))
password_field.click_here()
email_field.type_here("password@123")

submit_button = ScreenPoint(pos=(1127, 597))
submit_button.click_here()
```

