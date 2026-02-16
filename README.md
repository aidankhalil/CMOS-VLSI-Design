# CMOS-VLSI Design - 4x4 Bit-Sliced Array Multiplier

## Features
- Performed waveform validation across several rising-edge test vectors, verifying output propagation through delay cycles under realistic clock inputs.
- Integrated serial input/output via shift-register emulation to simulate test/debug mode, ensuring design testability and waveform reproducibility.

## Technologies & Skills Used
ASIC design, Cadence Virtuoso, waveform validation, digital logic, clock timing, testbench emulation, hardware engineering

## Setup Instructions
1. Open in Virtuoso or compatible simulation software
2. Load the layout and testbench
3. Simulate and observe waveform output

## Full Adder Reference (Standard FA Layout View)
![Full Adder Reference](https://github.com/user-attachments/assets/54c2e8d4-6c03-45fa-9ef6-a7209aa6d3b6)

## NxN Array Multiplier Reference
![Array_Multiplier_Reference](https://github.com/user-attachments/assets/85f14be7-59e1-49b7-8429-6b27de124c81)

## Final Layout
![Final Product](https://github.com/user-attachments/assets/5bb6e557-4cbb-482e-b366-54a7577058ed)

### Test Vector Results for 4x4 Bit Multiplier (Normal Mode | TEST = Low)

Outputs are shown in the following waveforms as **Q9-P(Q16)**, where P (*aka* 'Q16') is the MSB and Q9 the LSB.
Input bits *Q1-Q8* were not plotted, as selecting only X*in*, Y*in*, and CLK was more convenient.
Most of these waveforms require a few clock cycles to take into account the component delays before outputting the product (i.e. after the fifth rising edge of Test Vector 1..)

## **Test Vector 1**  
**Calculation:**  
`(1001)₂ * (1001)₂ = (0101 0001)₂`  
![test_vector_1](https://github.com/user-attachments/assets/5addcfc2-48b2-4f32-830d-af6fc6eafcac)  
**Explanation:**  
`9₁₀ * 9₁₀ = 81₁₀ = 0101 0001₂`

---

## **Test Vector 2**  
**Calculation:**  
`(1111)₂ * (0011)₂ = (0010 1101)₂`  
![test_vector_2](https://github.com/user-attachments/assets/1e1f2396-f35b-4ae2-8722-a76ad490db78)  
**Explanation:**  
`15₁₀ * 3₁₀ = 45₁₀ = 0010 1101₂`

---

## **Test Vector 3**  
**Calculation:**  
`(1001)₂ * (1011)₂ = (0110 0011)₂`  
![test_vector_3](https://github.com/user-attachments/assets/53f4a64d-28ba-49df-bd60-bcf63c9988bb)  
**Explanation:**  
`9₁₀ * 11₁₀ = 99₁₀ = 0110 0011₂`

---

## **Test Vector 4**  
**Calculation:**  
`(0011)₂ * (0011)₂ = (0000 1001)₂`  
![test_vector_4](https://github.com/user-attachments/assets/088e4356-f1df-45e1-8baa-c420c53604d3)  
**Explanation:**  
`3₁₀ * 3₁₀ = 9₁₀ = 0000 1001₂`

---

## **Test Vector 5**  
**Calculation:**  
`(1111)₂ * (1111)₂ = (1110 0001)₂`  
![test_vector_5](https://github.com/user-attachments/assets/5fa7a3f4-5030-4abf-a140-5f3e85e8dd85)  
**Explanation:**  
`15₁₀ * 15₁₀ = 225₁₀ = 1110 0001₂`

---

## **Test Vector 6**  
**Calculation:**  
`(0000)₂ * (0000)₂ = (0000 0000)₂`  
![test_vector_6](https://github.com/user-attachments/assets/65833124-67ae-41ce-9586-c13e8025d82e)  
**Explanation:**  
`0₁₀ * 0₁₀ = 0₁₀ = 0000 0000₂`

---

## **Test Vector 7**  
**Calculation:**  
`(1111)₂ * (0000)₂ = (0000 0000)₂`  
![test_vector_7](https://github.com/user-attachments/assets/0aa84043-c9c4-418b-9b94-ef6ed393e2ac)  
**Explanation:**  
`15₁₀ * 0₁₀ = 0₁₀ = 0000 0000₂`

---

## **Test Vector 8**  
**Calculation:**  
`(1001)₂ * (0011)₂ = (0001 1011)₂`  
![test_vector_8](https://github.com/user-attachments/assets/f93b6698-654f-4149-9eb9-3de2658d0c72)  
**Explanation:**  
`9₁₀ * 3₁₀ = 27₁₀ = 0001 1011₂`

---



### Test Mode (TEST=1)

In **Test Mode**, inputs are loaded serially via a **SIPO register**, and outputs are transmitted serially using a **PISO register**.  
This mode is used for debugging and verifying the multiplier's functionality.

### Example:
- **Test Mode = HIGH**:  
  ![testModeHigh](https://github.com/user-attachments/assets/8e855ac0-1821-4862-bd47-d4d3bb789df4)

- **Registers Testing | ALL HIGH**:  
  ![allHighTEST](https://github.com/user-attachments/assets/ff9e8d54-bb89-4395-ad81-12b2abe03d35)

- **Registers Testing | ALL LOW**:  
  ![allLowTEST](https://github.com/user-attachments/assets/9fbe1aee-d42d-403a-8f59-c9d70b582bd4)
