<h1>Algorithm for file updates in Python</h1>

<h2>Description</h2>
In this scenario, I was tasked to maintain and regularly update a file that is responsible for granting access to restricted patient records at a healthcare company. Employees are restricted access by their IP address.
<br />


<h2>Language Used</h2>

- <b>Python</b> 

<h2>Program walk-through:</h2>

<p align="center">
First I assigned the name of the file as a string to a variable: <br/>
<img src="https://i.imgur.com/AkpUD98.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After that I opened it with the with statement:  <br/>
<img src="https://i.imgur.com/lXz3aqb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
  I used the open function in read(“r”)mode, to read the contents of the file, so I can access the IP address stored in it. The with statement also helps manage the resources by closing the file after I exited it. The open function has another parameter called Import_file in this instance. This parameter indicates which file I want to import. The code also has an as keyword which is assigned to a variable named: file. This variable stores the output while I work with the with statement.  <br/>
<br />
<br />
To be able to read the file properly I converted it into a string with the .read()method: <br/>
<img src="https://i.imgur.com/w226pV4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <p align="center">
  I applied the .read() method to the file  variable in the with statement.
Then I assigned file.read() output to the ip_addresses variable.
The read happens in string format so I can work with it later on.
<br />
<br />
In order to be able to add and remove the IP addresses from the file more simply, I need the content in list format. I used the .split() method to convert from string to list:  <br/>
<img src="https://i.imgur.com/Mwmkquv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
    <p align="center">
    By default, the .split() function splits the text by whitespace into list elements.
I stored this list in the variable ip_addresses.
<br />
<br />
I used a for loop to iterate through the elements of the list:  <br/>
<img src="https://i.imgur.com/XCTfbLW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
       <p align="center">
      The for loop repeats code for a specified sequence.
The in keyword indicates to iterate through the sequence ip_addresses and assign each value to the loop variable element.
<br />
<br />
The algorithm also requires removing elements from ip_addresses that are also in the remove_list:  <br/>
<img src="https://i.imgur.com/4ovTYZt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
         <p align="center">
         First I created a conditional to check if the variable element was found in ip_addresses.
I did this because applying .remove() to elements that were not found in ip_addresses would result in an error.
Then I applied .remove() to ip_addresses. I passed in element as the loop variable so that each IP address that was in the remove list would be removed from ip_addresses.
<br />
<br />
Finally I updated the allow list file with the revised list of IP addresses. In order to achieve this I needed to convert back to string. I used the .join() method to achieve this:  <br/>
<img src="https://i.imgur.com/8UK1stZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
           <p align="center">
           The .join() method combines all items in an iterable into a string. I used the .join() method to create a string from the list ip_addresses so that I could pass it in as an argument to the .write() method when writing to the file "allow_list.txt".
I used the “ “ element as the separator.
<p align="center">
Then I used another with statement with the .write() to update the file.
<img src="https://i.imgur.com/X1rsxE6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <p align="center">
  This time I used “w” to be able to write over its content.
The .write function writes string data to a file and replaces any content the file has.
In this case I replaced the pre existing allow list in “allow_list.txt” with the updated one so the access permission is updated for the right employees.
<h2>Summary:</h2>
I created an algorithm to automate the updating of the access permission of a restricted file.
Achieving this by opening the file, converting it to a string, looping through it to check if the IP address was still valid or in the remove list, then converting back to string and removing the outdated IP’s.
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
