# cmsc312-assignment-3-multi-process-and-multi-threaded-print-server-solved
**TO GET THIS SOLUTION VISIT:** [CMSC312 Assignment 3-Multi-process and multi-threaded print server Solved](https://www.ankitcodinghub.com/product/cmsc-312-assignment-3-multi-process-and-multi-threaded-print-server-9010-points-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;115336&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CMSC312 Assignment 3-Multi-process and multi-threaded print server  Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
What is a print server?

• Consider a single globally shared printer queue that all processes and threads can read from or write into. The print queue has a finite size of 30 print jobs.

• Producer-Consumer problem: user processes versus consumer threads.

• The user processes act as producers and add print requests into the queue. Each print request is characterized by it’s size (in bytes). Each user can submit upto 30 print jobs; use a random number generator to determine the number of jobs for each user. For each print job, use another random number generator to find the size (in bytes) of that print request (between 100-1000 bytes).

• The different printers serve as consumers and run on different threads. Each such printer can process a print job and removes it from the global print queue.

• The main process will read the command line to determine the parameters, start the producer processes and consumer threads, and acts like an interactive command console. It also initializes the print queue but cannot modify it after initialization.

• The command line parameters include: (i) number of producer (user) processes, and (ii) number of printer (consumer) threads. Use nanosleep() or sleep() utilities to simulate a random delay (between 0.1 – 1sec) between two successive print jobs submitted by the same user. The user process inserts the print request into the global print queue; additional book-keeping parameters are allowed to be inserted. Hence, use a struct for the producer print request and the global queue will be an array or linked list of structs; similarly, use a struct for the consumer to process a print request. The producer processes cannot remove anything or update a currently existing print request from the queue.

• Each of the printer threads will process one print request at a time depending on their availability for as long as the queue is not empty. You need three semaphores (i) to check if the queue is full, (ii) to check if the queue is empty and (iii) for reading/writing the same queue element. You need to initialize these semaphores before starting the processes/threads. Since the semaphores need to be shared between the processes and threads, set them up on shared memory. Use your implementation of counting semaphores from Assignment-2 for the counting semaphores needed in this exercise.

If you face problems with the semaphores on shared memory, use the named semaphores method shown here: https://stackoverflow.com/questions/8359322/how-to-sharesemaphores-between-processes-using-shared-memory

This approach uses sem_open() calls instead of sem_init(). It is quick and easy.

No need to create shared memory separately for your gate1/mutex1 or gate2/mutex2 or the buffer_mutex variables. You still need shared memory for the “value” field of the triplet of variables that implement your counting semaphores though.

• Print out the results after all threads have completed. Specifically, we want how many print jobs and of what size each were sent to the print server by the user processes. Then for each printer (i.e., consumer thread), we want to check how many print jobs (and bytes) were actually processed.

• Use a signal handler in your code to ensure graceful termination of the threads on receiving a ^C from the console.

• Finally, turn in a report to show the execution times of your code as a function of the number of users (producers) and printers (consumers). Also, report the average waiting times for all the print jobs as a function of these metrics for BOTH the LIFO and FIFO queue implementations. Additionally, mention which portions of your code are not working in the report.

The global print queue: two implementations are needed.

• First use the global count concept for producer/consumer problems from Assignment-2 (maintained by the variable buffer_index). This is essentially the LIFO queue.

• Next use the FIFO queue implementation from Assignment-2.

Note: Late assignments will lose 5 points per day upto a maximum of 3 days. Code must compile and execute on the class Linux server.

Deliverables:

Output format:

For each job enqueued/dequeued, print out the following:

Producer &lt;process-id&gt; added &lt;job_size&gt; to buffer

Consumer &lt;consumer-id&gt; dequeue &lt;process-id, job_size&gt; from buffer

Also print out the total execution time and average waiting time at the end of your code.

Report format:

1) First give an outline of the working portions of your code. For each part not functioning list them out.

3) Third: show two sample runs of your code one for LIFO and other one for FIFO. Just copy-paste the code output from the server.

4) Finally, show the execution time and average waiting plots for LIFO and FIFO for different values of number of producer processes and number of consumer threads. Plots will be good to show here or you can simply use a table format; vary both #producers and #consumers.

5) Two options:

a. 3-D graph: you will just have a single 3-D graph for LIFO, and another 3-D graph for FIFO to report execution times.

b. 2-D graphs: 5 different graphs are needed for #producers = 2, 4, 6, 8, 10 respectively. In each graph, plot execution time VS number of consumers (varied as 2, 4, 6, 8, 10) for LIFO and for FIFO. So each 2-D graph will have two lines, one for LIFO and other one for FIFO.

Turn-in:

Submit two versions of your code: one for LIFO, other one for FIFO. Keep the output format (from above) the same for both implementations. Additionally, submit the report. All files must be uploaded through Canvas.

Bonus points:

You can get 10 bonus points if you implement the extension where each queue element is controlled by a separate binary semaphore. You need 30 additional binary semaphores to do this. Show the execution time improvements (if any) for this case.
