# Date/Time Stage.

Date/Time stage leverages Spark standard built-in date and timestamp functions which come in handy when we need
to make operations on date and time. 

All these operations accept input of type: date, timestamp or string. 
If string, it should be in a format that can be cast to date, such as `'yyyy-MM-dd'` 
and timestamp in `'yyyy-MM-dd'` `'HH:mm:ss.SSSS'`. 
It returns date and timestamp respectively. 

Null is returned if the input data was a string that could not be cast to date or timestamp.