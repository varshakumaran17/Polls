# Ex02 Django Polls
## Date: 19-11-2024

## AIM
To develop a Django application to implement polls.


## DESIGN STEPS

### STEP 1:
Clone the problem from GitHub

### STEP 2:
Create a new app in Django project

### STEP 3:
Enter the code for admin.py and models.py

### STEP 4:
Execute Django admin and create details for polls.

## PROGRAM
## admin.py
```
from django.contrib import admin
from .models import Question
admin.site.register(Question)
```
## models.py
```
from django.db import models
from django.utils import timezone  # Import timezone
import datetime  # Import datetime for time calculation
 
class Question(models.Model):
    question_text = models.CharField(max_length=200)
    pub_date = models.DateTimeField('date published')

    def _str_(self):
        return self.question_text

    def was_published_recently(self):
        """Returns True if the question was published recently."""
        return self.pub_date >= timezone.now() - datetime.timedelta(days=1)
  
class Choice(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)
  
    def _str_(self):
        return self.choice_text
```
## OUTPUT
![Screenshot (74)](https://github.com/user-attachments/assets/0efd6531-cf4f-4298-b1ee-000fa1f4cbcb)
![Screenshot (75)](https://github.com/user-attachments/assets/6cd66055-7334-4696-aa12-474fd268f541)
![Screenshot (76)](https://github.com/user-attachments/assets/c1a87c80-cf8b-4cee-86f6-56cf97d2ad9a)


## COURSERA GRADE

![Screenshot (73)](https://github.com/user-attachments/assets/a51134df-a20c-4fc4-8602-850d70b97cc8)

## RESULT
Thus the program for creating a polls using Django has been executed successfully.
