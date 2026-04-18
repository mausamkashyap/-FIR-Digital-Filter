# -FIR-Digital-Filter

**Design and Simulation of a Digital FIR Filter**

A Digital Finite Impulse Response (FIR) filter is one of the most important components in digital signal processing systems. It is widely used for applications such as noise reduction, signal smoothing, and frequency shaping. In this project, an FIR filter was designed and simulated using MATLAB, and its hardware implementation was carried out using Verilog in Xilinx Vivado.

The fundamental principle of an FIR filter is based on a weighted sum of present and past input samples. The output of the FIR filter is expressed as a linear convolution of the input signal with a finite set of coefficients. Mathematically, it is represented as:

y[n] = h[0]x[n] + h[1]x[n−1] + h[2]x[n−2] + … + h[N−1]x[n−(N−1)]

where x[n] is the input signal, h[n] represents the filter coefficients, and y[n] is the output signal. Since the filter has no feedback elements, it is inherently stable and easier to design compared to Infinite Impulse Response (IIR) filters.

In the first phase of the project, the FIR filter was designed using MATLAB. A low-pass filter was selected to demonstrate noise removal capability. The filter coefficients were generated using the built-in fir1() function by specifying the filter order and cutoff frequency. An input signal consisting of a low-frequency sine wave combined with a high-frequency noise component was created. This allowed observation of how effectively the filter removes unwanted frequency components.

The MATLAB simulation produced three important results: the input signal, the filter coefficients, and the filtered output signal. The input signal showed noticeable high-frequency noise, while the output signal appeared smoother, indicating successful filtering. Additionally, the frequency response of the filter was analyzed using visualization tools, which confirmed that high-frequency components were attenuated while low-frequency components were preserved.

In the second phase, the FIR filter was implemented in Verilog to simulate its hardware behavior. A 4-tap FIR filter structure was used for simplicity and clarity. The design consisted of shift registers (delay elements), multipliers for coefficient multiplication, and an adder to accumulate the results. At each clock cycle, the input signal was shifted through registers, multiplied with predefined coefficients, and summed to produce the output.

The Verilog design was simulated using Xilinx Vivado. A testbench was created to apply a sequence of input values and observe the output waveform. The simulation results confirmed that the output followed the expected FIR equation, producing a weighted sum of current and previous inputs. The waveform clearly demonstrated the delay effect and accumulation process, validating the correctness of the design.

From a performance perspective, FIR filters offer several advantages. They are always stable due to the absence of feedback loops, and they can be designed to have a linear phase response, which is crucial in many signal processing applications. However, FIR filters require more computational resources, as each additional tap increases the number of multipliers and adders required in hardware. This can lead to higher power consumption and area in VLSI implementations.

In conclusion, this project successfully demonstrated both the theoretical and practical aspects of FIR filter design. MATLAB was used for algorithm-level design and analysis, while Verilog and Xilinx Vivado were used for hardware-level implementation and simulation. The results verified that the FIR filter effectively removes noise and produces a stable, reliable output, making it suitable for a wide range of digital signal processing applications.


Outcome:
