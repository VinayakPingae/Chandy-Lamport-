Name - Vinayak Subhash Pingale
Email - vpingal1@binghamton.edu

Languages Used - Java

Implementation Details

In the first part, you will implement a distributed banking application. The distributed bank has multiple branches. Every branch knows about all other branches. Each branch starts with some initial balance. It then randomly selects a branch and send a random amount of money to this branch at unpredictable times. You must implement the following functions for a branch in a distributed bank:

In the second part, you will use the Chandy-Lamport global snapshot algorithm take global snapshots of your bank. In case of the distributed bank, a global snapshot will consist of the local state of each branch (i.e., its balance) and the amount of money in transit on all communication channels. Each branch will be responsible for recording and reporting its own local state (balance) as well as the total money in transit on each of its incoming channels. For simplicity, in this project, the controller will contact one of the branches to initiate the global snapshot. It does so by making a initSnapshot call to the selected branch. The selected branch will then initiate the snapshot by first recording its own local state and send out marker messages to all other branches. After some time (long enough for the snapshot algorithm to finish), the controller makes retrieveSnapshot calls to all branches to retrieve their recorded local and channel states. Note that if the snapshot is correct, the total amount ofmoney in all branches and in transit should equal to the command line argument given to the controller.

Sample Output
=================

remote01:~/vpinga11/src> bash
vpingal1@remote01:~/vpinga11/src$ ./controller.sh 4000 branches.txt
branch1 remote01.cs.binghamton.edu 10000
branch2 remote01.cs.binghamton.edu 10001
branch3 remote01.cs.binghamton.edu 10002
branch4 remote01.cs.binghamton.edu 10003
[BranchID(name:branch1, ip:remote01.cs.binghamton.edu, port:10000), BranchID(name:branch2, ip:remote01.cs.binghamton.edu, port:10001), BranchID(name:branch3, ip:remote01.cs.binghamton.edu, port:10002), BranchID(name:branch4, ip:remote01.cs.binghamton.edu, port:10003)]
Initial Amount assigned to Branch branch1 is 1000
Initial Amount assigned to Branch branch2 is 1000
Initial Amount assigned to Branch branch3 is 1000
Initial Amount assigned to Branch branch4 is 1000
Initial Amount assigned to Branch branch1 is 1000
Initial Amount assigned to Branch branch2 is 1000
Initial Amount assigned to Branch branch3 is 1000
Initial Amount assigned to Branch branch4 is 1000
Initial Amount assigned to Branch branch1 is 1000
Initial Amount assigned to Branch branch2 is 1000
Initial Amount assigned to Branch branch3 is 1000
Initial Amount assigned to Branch branch4 is 1000
Initial Amount assigned to Branch branch1 is 1000
Initial Amount assigned to Branch branch2 is 1000
Initial Amount assigned to Branch branch3 is 1000
Initial Amount assigned to Branch branch4 is 1000
SnapShot for SnapShot Number : 1
LocalSnapshot(snapshot_num:1, balance:959, messages:[])
====================================================================
SnapShot for SnapShot Number : 1
LocalSnapshot(snapshot_num:1, balance:1038, messages:[])
====================================================================
SnapShot for SnapShot Number : 1
LocalSnapshot(snapshot_num:1, balance:1042, messages:[19])
====================================================================
SnapShot for SnapShot Number : 1
LocalSnapshot(snapshot_num:1, balance:942, messages:[])
====================================================================
SnapShot for SnapShot Number : 2
LocalSnapshot(snapshot_num:2, balance:971, messages:[])
====================================================================
SnapShot for SnapShot Number : 2
LocalSnapshot(snapshot_num:2, balance:1075, messages:[31])
====================================================================
SnapShot for SnapShot Number : 2
LocalSnapshot(snapshot_num:2, balance:1014, messages:[])
====================================================================
SnapShot for SnapShot Number : 2
LocalSnapshot(snapshot_num:2, balance:909, messages:[])
====================================================================
SnapShot for SnapShot Number : 3
LocalSnapshot(snapshot_num:3, balance:1005, messages:[])
====================================================================
SnapShot for SnapShot Number : 3
LocalSnapshot(snapshot_num:3, balance:1194, messages:[9])
====================================================================
SnapShot for SnapShot Number : 3
LocalSnapshot(snapshot_num:3, balance:878, messages:[])
====================================================================
SnapShot for SnapShot Number : 3
LocalSnapshot(snapshot_num:3, balance:914, messages:[])
====================================================================
SnapShot for SnapShot Number : 4
LocalSnapshot(snapshot_num:4, balance:1118, messages:[])
====================================================================
SnapShot for SnapShot Number : 4
LocalSnapshot(snapshot_num:4, balance:1013, messages:[])
====================================================================
SnapShot for SnapShot Number : 4
LocalSnapshot(snapshot_num:4, balance:956, messages:[])
====================================================================
SnapShot for SnapShot Number : 4
LocalSnapshot(snapshot_num:4, balance:913, messages:[])
====================================================================
SnapShot for SnapShot Number : 5
LocalSnapshot(snapshot_num:5, balance:1137, messages:[])
====================================================================
SnapShot for SnapShot Number : 5
LocalSnapshot(snapshot_num:5, balance:1056, messages:[])
====================================================================
SnapShot for SnapShot Number : 5
LocalSnapshot(snapshot_num:5, balance:926, messages:[])
====================================================================
SnapShot for SnapShot Number : 5
LocalSnapshot(snapshot_num:5, balance:881, messages:[])
====================================================================
^Z
[1]+  Stopped                 ./controller.sh 4000 branches.txt
vpingal1@remote01:~/vpinga11/src$                                                                                                              