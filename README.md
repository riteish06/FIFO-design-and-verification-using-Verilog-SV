# FIFO-design-and-verification-using-Verilog-SV
 Synchronous FIFO:
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
