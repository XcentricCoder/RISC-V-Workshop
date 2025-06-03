# Digital Logic with TL-Verilog and Makerchip

# Logic gates
 Logic gate is a fundamental building block in digital circuits, acting as a simple electronic switch or circuit that operates on binary inputs (0 or 1) to produce a binary output based on a specific logical rule. These gates implement Boolean algebra and are crucial for creating more complex digital systems like computers and other electronic devices. From these we can make more gates such as NAND,NOR,XOR and XNOR etc.


 

 # Combinational Logic
A combinational logic circuit is a type of digital circuit where the output at any given moment depends on the current combination of its inputs. It lacks memory, meaning the output is not influenced by the past states of the inputs. These circuits are built using logic gates like AND, OR, NOT, NAND, and NOR.




 # Sequential Logic
 A sequential logic circuit is a digital circuit whose output depends not only on the present input but also on the past inputs and the internal state of the circuit. It incorporates memory elements, like flip-flops or latches, to store the previous state, allowing the circuit to "remember" past inputs. This contrasts with combinational logic, where the output is solely determined by the current inputs.


 

 # Storage elements: Flip-Flops
 In digital electronics, a flip-flop is a fundamental memory circuit that can store a single bit of information (0 or 1) and can be toggled between these two states. It's like a basic switch that can be flipped on or off, retaining that state until an external signal (like a clock pulse) triggers a change. Flip-flops are bistable devices, meaning they have two stable states. They can hold a specific binary value (0 or 1) until a control signal causes them to change.





 # Validity
 Validity is the device meets the needs and requirements of its intended users and the intended use environment. In a chip there are maximum things that are not useful and sit idle in the chip, but the power still goes in them, which is a wastage of electricity. Validity fixes this problem by eliminating the non-useful gates.



 # Lab 3
 ## 1. Combinational Calculator
        $sum[31:0] = $val1[31:0] + $val2[31:0];
    		$diff[31:0] = $val1[31:0] - $val2[31:0];
    		$prod[31:0] = $val1[31:0] * $val2[31:0];
    		$quot[31:0] = $val1[31:0] / $val2[31:0];
      $out[31:0] = $op[0] ? $sum : $op[1] ? $diff : $op[2] ? $prod : $qout ;


   ![Combi_Calc](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/Day-3/Screenshot%20from%202025-05-27%2006-44-54.png)


 ## 2. Sequential Calculator
         
    $sum[31:0] = $val1[31:0] + $val2[31:0];
    $diff[31:0] = $val1[31:0] - $val2[31:0];
    $prod[31:0] = $val1[31:0] * $val2[31:0];
    $quot[31:0] = $val1[31:0] / $val2[31:0];
    $out[31:0] = $op[0] ? $sum : $op[1] ? $diff : $op[2] ? $prod : $qout ;
    $out[31:0] = $val1[31:0];

  ![Seq_Calc](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/Day-3/Screenshot%20from%202025-06-03%2019-25-57.png)


  ## 3. Fibonacci Calculator
  
    $num[31:0] = $reset ? 1: (>>1$num + >>2$num );


   ![Fibonacci_Calc](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/Day-3/Screenshot%20from%202025-06-03%2019-34-59.png)
      

  ## 4. Pythagorean Theorem Pipeline
    |calc
 		 			 @1
     			   $aa_sq[7:0] = $aa[3:0] ** 2;
    			    $bb_sq[7:0] = $bb[3:0] ** 2;
 			    @2
     			   $cc_sq[8:0] = $aa_sq + $bb_sq;
 			    @3
     			   $cc[4:0] = sqrt($cc_sq);
    

   ![Pyth_thm](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/Day-3/Screenshot%20from%202025-05-27%2022-17-53.png)

  ## 5.Final calculator with validity and memory

            @0
         $reset = *reset;
              
        
      @1
         $valid[0:0] = $reset ? '0 : >>1$valid + 1;
         $valid_or_reset = $valid || $reset;
         $val2[31:0] = $rand2;
         $val1[31:0] = >>2$out;
         ?$valid_or_reset
            $sum[31:0] = $val1[31:0] + $val2[31:0];
            $diff[31:0] = $val1[31:0] - $val2[31:0];
            $prod[31:0] = $val1[31:0] * $val2[31:0];
            $quot[31:0] = $val1[31:0] / $val2[31:0];
         
      @2 
         ?$valid_or_reset
            $out[31:0] = $reset ? '0:
                         $op[2:0] == 0 ? $sum:
                         $op[2:0] == 1 ? $diff:
                         $op[2:0] == 2 ? $prod:
                         $op[2:0] == 3 ? $div:
                         $op[2:0] == 4 ? >>2$mem : >>2$out;
            $mem[31:0] = $reset ? '0 : $op[2:0] == 5 ? $val1: (>>2$mem);

   ![Calc_mem_val](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/Day-3/Screenshot%20from%202025-06-03%2020-44-04.png)
