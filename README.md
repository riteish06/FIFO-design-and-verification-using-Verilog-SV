# FIFO-design-and-verification-using-Verilog-SV
# Synchronous FIFO:
1. Synchronous FIFO can be implemented in hardware or software.
2. Hardware implementation is faster but less flexible, while software implementation is slower but more flexible.
3. The synchronous FIFO module in this project is implemented in Verilog HDL and has a variable-length buffer with scalable register word width and address space.
4. The module has flags to notify the buffer of its full/empty status and almost empty/almost full watermark flags to help prevent read/write errors.
# Architecture:
1. The FIFO is made up of a memory array, flag logic, read control logic, and write control logic.
2. The memory array is an array of flip-flops that stores the data.
3. The flag logic generates flags to indicate the status of the FIFO, such as empty, full.
4. The read control logic and write control logic control the read and write operations to the FIFO.
#Implementation (Design and Verification):
1. The synchronous FIFO design involves implementation of a memory array and associated write/read control logic at the RTL level using Verilog HDL.
2. A verification environment is developed using SystemVerilog to verify the functionality of the Synchronous FIFO design model.
3. A proper verification environment thoroughly checks on proper functioning of the design, and requires the verification engineers to create systematic and automated test benches.
4. This project describes the approach for implementing a verification environment for the synchronous FIFO. It also describes the implementation of constrained random test stimuli and functional coverage.
