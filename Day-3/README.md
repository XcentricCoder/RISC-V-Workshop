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


      ![Combi_Calc]()


  

   

 
