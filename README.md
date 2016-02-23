Application-Sandboxer
---------------------

This is a simple SandBoxing Application developed using POSIX API's for running any binary file safely.

Build Instructions:- 

The file uses some commands of c++11. So use ths flag -std=c++11 while compiling.<br />
Comilation Command:- `g++ final_v.cpp -w -std=c++11`

Update :- Added makefile. Just type make in terminal and Voila!.


File Structure
--------------

There are basically three files which constitute the whole project.

An open source .so file has been imported from Sharif-Judge. This file is imported only for a very specific 
purpose in the sandbox. Rest depends upon `final_v.cpp` and `parse.cpp`. All the functions are defined in the 
file `parse.cpp` and are used in the file `final_v.cpp`. Whenever you run any command using it, it takes comamnd 
line input for the process to be ran and allowed resource limits. Then it periodically checks for the resource being
used by that process and the child process it creates. If at any time the combined resource usage of that process family
exceeds the limts, all the processes in the family are terminated.

All the other files are basically for testing purposes.

Using
-----

Run the .out file generated by compiling the final_v.cpp file with the following flags:-

-t or --time ## - sets the max time limit of the Black-Box Process<br />
-m or --memory ## - sets the maximum memory that can be consumed by the Black-Box process. <br />
-f or --frquency ## - sets the frequency of polling the resources being used by the process.<br />
-d or --debug - set the debug flag(You will see the result of each Poll with the frequency you set.)<br />
Replace ## with your preferred values.

Memory limits are in KB, Time limits are in Clock Ticks, and frequency is in seconds.

Running:-
eg. if you want to run firefox with time clocks - 1000, memory 1000000 KB's and frequency 0.5 s
run - <br />
`./a.out -t 1000 -m 10000000 -f 0.1 -d firefox`

NOTE:- If you want to restrict the Black-Box from using Network, Add unshare -n before the command as:-<br />

`unshare -n ./a.out -t 1000 -m 10000000 -f 0.1 -d firefox`

Features to be Added:-
----------------------
To be updated.