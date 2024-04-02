# HALF_ADDER
## AIM
#### To Simulate the Half Adder using Vivado software
## APPARATUS REQUIRED
#### Vivado 2023.2 Software
## PROGRAM  
     module HA(a,b,sum,carry);
     input a,b;
     output sum,carry;
     xor g1(sum,a,b);
     and g2(carry,a,b);
     endmodule
## Truth Table
![image](https://github.com/RESMIRNAIR/HALF_ADDER/assets/154305926/fe672c28-5c6a-4355-b70f-b40bce63880d)
## Circuit Diagram
![image](https://github.com/RESMIRNAIR/HALF_ADDER/assets/154305926/5f1a79a7-73c2-4b99-a40d-afa2a20c74ac)
## OUTPUT
![half adder output](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/34bf5e77-672b-4131-a606-e91460b8e10e)
# Elaborated Circuit Diagram
![half adder design](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/68c03aa0-8415-426b-88a0-c50fdb5e90ba)

## RESULT
#### Thus the halfadder program is studied and simulated using the software successfully

# FULL ADDER
## AIM
#### To Simulate the Half Adder using Vivado software
## APPARATUS REQUIRED
#### Vivado 2023.2 Software
 ## PROGRAM
    module FA(a,b,c,sum,carry);
    input a,b,c;
    output sum,carry;
    assign sum=a^b^c;
    assign carry=(a&b)|(b&c)|(c&a);
    endmodule 

# Truth Table
![image](https://github.com/RESMIRNAIR/FULL_ADDER/assets/154305926/02ead8f5-d958-4c89-ac51-368ca086cf41)
# Circuit Diagram
![image](https://github.com/RESMIRNAIR/FULL_ADDER/assets/154305926/418e00aa-ed19-4ab3-a413-bae9575bff0e)
![image](https://github.com/RESMIRNAIR/FULL_ADDER/assets/154305926/0c26fe47-d78c-43dd-ac0d-804e427a3bbc)
## OUTPUT
![full adder output](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/9a325104-e7cd-4134-ac5a-1ea6840968ef)
# Elaborated Circuit Diagram
![full adder design](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/38e5e2b1-6356-44a3-9f2a-5992fa223337)

## RESULT
#### Thus the fulladder  program is studied and simulated using the software successfully

# HALF SUBTRACTOR
## AIM
#### To Simulate the Half Subtractor using Vivado software
## APPARATUS REQUIRED
#### Vivado 2023.2 Software

# PROGRAM
    module half_subtractor(
    input A,
    input B, 
    output Diff, 
    output Borrow 
    );

    assign Diff = A ^ B;
    assign Borrow = ~A & B; 
    endmodule
# Truth Table
![image](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/e2723d53-637c-4a27-bc05-8dc4abf65d61)
# Circuit Diagram
![image](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/e679bf7c-3d51-4248-9707-20ab07e92699)
![image](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/56520178-36bd-4f0d-82f5-88d1594619d1)
# OUTPUT
![half subtractor output](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/8bc9f58c-6de7-422b-a27c-3e27b71a2ecd)
# Elaborated Circuit Diagram
![half subtractor design](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/5e6f0789-26a5-4676-a2a5-1df5447dfb2b)

## RESULT
#### Thus the halfsubtractor  program is studied and simulated using the software successfully

# FULL SUBTRACTOR
## AIM
#### To Simulate the Full Subtractor using Vivado software
## APPARATUS REQUIRED
#### Vivado 2023.2 Software

 # PROGRAM 
    module full_subtractor(
    input A, // Minuend
    input B, // Subtrahend
    input Cin, // Borrow input
    output Diff, // Difference
    output Bout // Borrow output
    );

    wire D1, B1, B2;
    
    // First half subtractor
    half_subtractor HS1(.A(A), .B(B), .Diff(D1), .Borrow(B1));
    
    // Second half subtractor
    half_subtractor HS2(.A(D1), .B(Cin), .Diff(Diff), .Borrow(B2));
    
    // OR gate to compute final borrow output
    assign Bout = B1 | B2;
    endmodule
 # Truth Table  And Circuit Diagram    
![image](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/bcd29542-b0ce-46f3-bf07-5ce97223fa5d)
#  OUTPUT
![full subtractor output](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/6afedcaa-90b2-4754-8d3b-36ff3dbedfce)
# Elaborated Circuit Diagram
![full subtactor design](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/8315e8a1-5380-446c-8d28-735e9d97b4b7)

## RESULT
#### Thus the fullsubtractor  program is studied and simulated using the software successfully

# DECODER
## AIM
#### To Simulate the Decoder using Vivado software
## APPARATUS REQUIRED
#### Vivado 2023.2 Software

 # PROGRAM
    module decoder_2to4(
    input [1:0] select_in, // Select input
    output reg [3:0] data_out // Decoded output
    );
    
    always @* begin
        case(select_in)
            2'b00: data_out = 4'b0001; // Output at index 0
            2'b01: data_out = 4'b0010; // Output at index 1
            2'b10: data_out = 4'b0100; // Output at index 2
            2'b11: data_out = 4'b1000; // Output at index 3
            default: data_out = 4'bxxxx; // Invalid input, outputs all 'x'
        endcase
    end
    
    endmodule
   # Truth Table And Circuit Diagram
   ![image](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/670c4073-9d6a-4412-94c7-879505f1bdfa)
   # OUTPUT
   ![decoder output](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/c5b79e9c-9acd-4f82-aded-88af6a6da4f3)
   # Elaborated Circuit Diagram
   ![decoder design](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/49aab787-0327-40aa-a763-c88be804a226)

   ## RESULT
   #### Thus the Decoder  program is studied and simulated using the software successfully

   # ENCODER
   ## AIM
   #### To Simulate the Encoder using Vivado software
   ## APPARATUS REQUIRED
  #### Vivado 2023.2 Software

 # PROGRAM
    module encoder_3to1(
    input [2:0] data_in, // Input data
    output [1:0] encoded_out // Encoded output
    );
    
    assign encoded_out[0] = |data_in; // Bitwise OR operation on all input bits
    assign encoded_out[1] = &data_in; // Bitwise AND operation on all input bits
    
    endmodule
 # Truth Table 
 ![image](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/4bf3305c-cf83-49a8-93c4-c85662e7833b)
 # Circuit Diagram
 ![image](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/e24ae5e1-efa8-47a5-aac8-75b721b18422)
# Elaborated Circuit Diagram
![encoder design](https://github.com/NitheshKumar-B/EXP-1/assets/161724980/79532a11-43a1-4153-9eea-3b6df89c5e83)
 ## RESULT
   #### Thus the Encoder  program is studied and simulated using the software successfully
