2_1_1: Create Deadlock - Instead of using mutex semaphore, every philosopher should 
    lock both forks when he takes them. This will significantly increase 
    the chance of Deadlock, since everyone may take the right fork and wait 
    for the left fork.
    
2_1_2: Solve Deadlock - forks will be numbered 1 through 5 and each philosopher will 
    always pick up the lower-numbered fork first, and then the higher-numbered fork. 
    In this case, if four of the five philosophers simultaneously pick up their lower-numbered fork, 
    only the highest-numbered fork will remain on the table, so the fifth philosopher will not 
    be able to pick up any fork. Moreover, only one philosopher will have access to that highest-numbered fork, 
    so they will be able to eat using two forks. This method can cause starvation but it will never create deadlock.

2_2_1: create Starvation - By deleting the two lines waking up the nearby philosophers, 
    the first philosopher never wakes up the other philosophers. And so he ran alone 
    while they starving.
    
2_2_2: Solve Starvation - We have defined that any philosopher can take both forks only if all other 
    philosophers have put down their forks. The result is that all philosophers 
    eat one after the other. That is why there can never be a philosopher who will not eat. 
    While this is not an effective implementation of the problem, it is certainly 
    not possible to cause starvation here. 

2_3_1: Create Livelock - To create a livelock, we defined that each philosopher first takes 
    the fork to the right and then tries to take the fork to the left. 
    If after 5 seconds of trying to take the fork he fails, he will put down
    the right fork and wait for 5 seconds. This loop will be repeated 
    until the philosopher has both forks and can eat. When the five philosophers
    raise the right fork at the same time, a livelock will be created, 
    as they will constantly raise all the forks at the same time.
    
2_3_2: Solve Livelock - same implementation as 2_1_2. forks will be numbered 1 to 5 and each philosopher will 
   always pick up the lower-numbered fork first, and then the higher-numbered fork. 
   In this case philosophers can never get stuck. if four of the five philosophers simultaneously 
   pick up their lower-numbered fork, only the highest-numbered fork will remain on the table, 
   so the fifth philosopher will not be able to pick up any fork. Moreover, only one philosopher 
   will have access to that highest-numbered fork, so he will be able to eat using two forks. 
   Therefore, there will always be one philosopher who can progress and prevent a situation that the 
   system is not progressing. This method can cause starvation but it will never create Livelock.
