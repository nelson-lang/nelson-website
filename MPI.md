## Message Passing Interface

Distributed Computing with MPI:

- [mpiexec](/help/en_US/mpiexec.html) : Run an MPI script.
- [MPI_Allreduce](/help/en_US/MPI_Allreduce.html) : Combines values from all processes and distributes the result back to all processes.
- [MPI_Barrier](/help/en_US/MPI_Barrier.html) : Blocks until all processes in the communicator have reached this routine.
- [MPI_Bcast](/help/en_US/MPI_Bcast.html) : Broadcasts a message from the process with rank "root" to all other processes of the communicator
- [MPI_Comm_delete](/help/en_US/MPI_Comm_delete.html) : Removes MPI_Comm object.
- [MPI_Comm_get_name](/help/en_US/MPI_Comm_get_name.html) : Return the print name from the communicator.
- [MPI_Comm_object](/help/en_US/MPI_Comm_object.html) : Creates MPI_Comm object.
- [MPI_Comm_rank](/help/en_US/MPI_Comm_rank.html) : Determines the rank of the calling process in the communicator.
- [MPI_Comm_size](/help/en_US/MPI_Comm_size.html) : Determines the size of the group associated with a communicator.
- [MPI_Comm_split](/help/en_US/MPI_Comm_split.html) : Partitions the group that is associated with the specified communicator into a specified number of disjoint subgroups.
- [MPI_Comm_used](/help/en_US/MPI_Comm_used.html) : Returns list of current used MPI_Comm handle.
- [MPI examples](/help/en_US/MPI_examples.html) : Some Nelson MPI examples.
- [MPI_Finalize](/help/en_US/MPI_Finalize.html) : Terminate the MPI execution environment.
- [MPI_Get_library_version](/help/en_US/MPI_Get_library_version.html) : Return the version number of MPI library.
- [MPI_Get_processor_name](/help/en_US/MPI_Get_processor_name.html) : Gets the name of the processor.
- [MPI_Get_version](/help/en_US/MPI_Get_version.html) : Return the version number of MPI.
- [MPI_Init](/help/en_US/MPI_Init.html) : Initialize the MPI execution environment.
- [MPI_Initialized](/help/en_US/MPI_Initialized.html) : Indicates whether MPI_Init has been called.
- [MPI_Iprobe](/help/en_US/MPI_Iprobe.html) : Nonblocking test for a message.
- [MPI overview](/help/en_US/MPI_overview.html) : Access to MPI features from Nelson.
- [MPI_Probe](/help/en_US/MPI_Probe.html) : Blocking test for a message.
- [MPI_Recv](/help/en_US/MPI_Recv.html) : Blocking receive for a message.
- [MPI_Reduce](/help/en_US/MPI_Reduce.html) : Reduces values on all processes to a single value.
- [MPI_Send](/help/en_US/MPI_Send.html) : Performs a blocking send.

Example: Sum on distributed computing:

[Source MPI sum example](https://github.com/Nelson-numerical-software/nelson/blob/master/modules/mpi/examples/MPI_parallel_sum.nls)

![MPI Sum](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/MPI_parallel_sum.png "MPI")
![Task manager with process started by Nelson](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/task_manager.png "Task manager with process started by Nelson")

[Previous page](FEATURES.md)
