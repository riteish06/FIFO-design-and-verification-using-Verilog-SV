# FIFO-design-and-verification-using-Verilog-SV
# Synchronous FIFO:
Synchronous FIFO can be implemented with software or hardware. In the case of hardware
implementation, any adaption demands a new board layout. And software implementation
gives enough flexibility for adaption. When it comes to speed, hardware FIFO would be
preferred than software implementation. So, there always exists a trade-off in either of the
implementation.
For this project, the synchronous FIFO module [4] is implemented at the RTL level
using Verilog HDL, which has a variable-length buffer with scalable register word-width
and address space. Buffer depth and data width can be adjusted within the module’s
parameterization. This module helps in syncing two unrelated modules in a digital system
involving different clocks running at different speeds [5]. It has an ability to notify the
buffer when to slow down the read/write operation through almost empty/almost full
watermark flags. It also has flags to notify the buffer its full/empty status. These flags help
in preventing read/write errors. In the case of buffer empty status, read operation shouldn’t
be carried out. In the case of buffer full status, write operation shouldn’t be carried out.
# Architecture:
The building blocks of a synchronous FIFO include memory array and flag logic controlled
by the read control logic and the write control logic. An array of flip-flops forms the
memory array and width and depth expansion of the array can be achieved easily through
parameterization, as it is implemented in Software.
The FIFO module can efficiently handle two systems, one writing to the FIFO and one
reading from the FIFO, which are operating at different speeds. Simultaneous read and
write operations are possible through a request and acknowledgment based protocol. In the
case of a read operation, the read_request signal and r_enable signal help in successful
data read from the memory array. In the case of a write operation, the w_enable signal
helps in successful data write into the memory array.
There are two pointers, write_pointer and read_pointer, which help in steering the data
into and out of the memory array. They store the write and read address value associated
with the memory array. After each successful data write and / or read, the corresponding
pointer is incremented by one to point to the next address.
Those two address pointers are involved in flag logic. Flag logic[6] uses the information
in both the pointers to generate flags based on the comparison between the read address
pointer and the write address pointer. If the difference between the two pointers is zero,
the empty flag is asserted denoting the FIFO empty status. If the difference between the
two pointers is equal to the FIFO depth, the full flag is asserted denoting the FIFO full
status. Similarly, other flags such as almost full flag and almost empty flag are generated
by comparing the offset value specified in the program with the word count in the memory
array
