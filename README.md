# Digital_System_Lab_Final_Project
contributed by < [teammate](https://www.youtube.com/watch?v=dQw4w9WgXcQ) >

## target
扣
簡報
電路圖
Demo影片

### `Dot Matrix` :

dot_col_0

| [0,0] | [1,0] | [2,0] | [3,0] | [4,0] | [5,0] | [6,0] | [7,0] |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| [0,1] | [1,1] | [2,1] | [3,1] | [4,1] | [5,1] | [6,1] | [7,1] |
| [0,2] | [1,2] | [2,2] | [3,2] | [4,2] | [5,2] | [6,2] | [7,2] |
| [0,3] | [1,3] | [2,3] | [3,3] | [4,3] | [5,3] | [6,3] | [7,3] |
| [0,4] | [1,4] | [2,4] | [3,4] | [4,4] | [5,4] | [6,4] | [7,4] |
| [0,5] | [1,5] | [2,5] | [3,5] | [4,5] | [5,5] | [6,5] | [7,5] |
| [0,6] | [1,6] | [2,6] | [3,6] | [4,6] | [5,6] | [6,6] | [7,6] |
| [0,7] | [1,7] | [2,7] | [3,7] | [4,7] | [5,7] | [6,7] | [7,7] |

dot_col_1

| [0,0] | [1,0] | [2,0] | [3,0] | [4,0] | [5,0] | [6,0] | [7,0] |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| [0,1] | [1,1] | [2,1] | [3,1] | [4,1] | [5,1] | [6,1] | [7,1] |
| [0,2] | [1,2] | [2,2] | [3,2] | [4,2] | [5,2] | [6,2] | [7,2] |
| [0,3] | [1,3] | [2,3] | [3,3] | [4,3] | [5,3] | [6,3] | [7,3] |
| [0,4] | [1,4] | [2,4] | [3,4] | [4,4] | [5,4] | [6,4] | [7,4] |
| [0,5] | [1,5] | [2,5] | [3,5] | [4,5] | [5,5] | [6,5] | [7,5] |
| [0,6] | [1,6] | [2,6] | [3,6] | [4,6] | [5,6] | [6,6] | [7,6] |
| [0,7] | [1,7] | [2,7] | [3,7] | [4,7] | [5,7] | [6,7] | [7,7] |

### `keypad` :
| C | 9 | 8 | 7 |
| - | - | - | - |
| D | 5 | 6 | 4 |
| E | 3 | 2 | 1 | 
| F | B | A | 0 |

->use

|   |   |   |   |
| - | - | - | - |
|   |   |   |   |
|   | 3 |   |   | 
| F | B | A |   |

### `block_type & seven_segment_display` :


@
@
@
@
| X |   |   |
| - | - | - |
| X |   |   |
| X |   |   |
| X |   |   |
| X |   |   |

1.
@
@
@@
| X |   |   |
| - | - | - |
| X |   |   |
| X |   |   |
| X |   |   |
| X | X | X |

2.
@
@@
@
| X |   |   |
| - | - | - |
| X |   |   |
| X | X | X |
| X |   |   |
| X |   |   |

3.
@@
@
@
| X | X | X |
| - | - | - |
| X |   |   |
| X |   |   |
| X |   |   |
| X |   |   |

4.
@
@@
__@
| X |   |   |
| - | - | - |
| X |   |   |
| X | X | X |
|   |   | X |
|   |   | X |

5.
@@
@@
| X | X | X |
| - | - | - |
| X |   | X |
| X | X | X |
|   |   |   |
|   |   |   |

6.
__@
@@
@
|   |   | X |
| - | - | - |
|   |   | X |
| X | X | X |
| X |   |   |
| X |   |   |

7.
@@
@
@@
| X | X | X |
| - | - | - |
| X |   |   |
| X |   |   |
| X |   |   |
| X | X | X |

## framework

### `0.遊戲本體` :
* input
    * clock
    * reset
    * [3:0] keypad_col
* output
    * [3:0] keypad_row
    * [7:0] dot_row
    * [7:0] dot_col_0
    * [7:0] dot_col_1
    * [6:0] next_state
    * [6:0] score_1
    * [6:0] score_2
    * [6:0] score_3
* wire

### `1.除頻器` :heavy_check_mark: 
* input
    * clock
    * reset
* output
    * clk_div

### `2.keypad` :heavy_check_mark: 
* input
    * clock
    * reset
    * [3:0] keypad_col
* output
    * [3:0] keypad_row
    * [3:0] keypad_buffer

### `3.生成方塊` :
* input
* output

### `4.方塊掉落` :
* input
* output

### `5.控制方塊（左右下 旋轉` :
* input
* output

### `6.消除連線` :
* input
* output

### `7.計分器` :
* input
* output

### `8.seven segment display` :
* input
* output

### `9.dot matrix display` :
* input
* output

:::spoiler `pin_plan.tcl`
```verilog=
# set clock
set_location_assignment PIN_P11 -to clock;
# set reset
set_location_assignment PIN_B8 -to reset;

# set keypad row
set_location_assignment PIN_AB2 -to keypad_row[0];
set_location_assignment PIN_AB3 -to keypad_row[1];
set_location_assignment PIN_AA5 -to keypad_row[2];
set_location_assignment PIN_AA6 -to keypad_row[3];

# set keypad column
set_location_assignment PIN_Y5  -to keypad_col[0];
set_location_assignment PIN_Y4  -to keypad_col[1];
set_location_assignment PIN_Y3  -to keypad_col[2];
set_location_assignment PIN_AA2 -to keypad_col[3];

# set dot matrix row
set_location_assignment PIN_AA8  -to dot_row[0];
set_location_assignment PIN_AA10 -to dot_row[1];
set_location_assignment PIN_W10  -to dot_row[2];
set_location_assignment PIN_Y8   -to dot_row[3];
set_location_assignment PIN_V7   -to dot_row[4];
set_location_assignment PIN_W9   -to dot_row[5];
set_location_assignment PIN_V8   -to dot_row[6];
set_location_assignment PIN_W7   -to dot_row[7];

# set dot matrix column_0
set_location_assignment PIN_AB13 -to dot_col_0[0];
set_location_assignment PIN_AA14 -to dot_col_0[1];
set_location_assignment PIN_W5   -to dot_col_0[2];
set_location_assignment PIN_Y11  -to dot_col_0[3];
set_location_assignment PIN_W6   -to dot_col_0[4];
set_location_assignment PIN_AB12 -to dot_col_0[5];
set_location_assignment PIN_W12  -to dot_col_0[6];
set_location_assignment PIN_W13  -to dot_col_0[7];

# set dot matrix column_1
set_location_assignment PIN_AB10 -to dot_col_1[0];
set_location_assignment PIN_AA15 -to dot_col_1[1];
set_location_assignment PIN_V5   -to dot_col_1[2];
set_location_assignment PIN_Y7   -to dot_col_1[3];
set_location_assignment PIN_W8   -to dot_col_1[4];
set_location_assignment PIN_AA9  -to dot_col_1[5];
set_location_assignment PIN_AB11 -to dot_col_1[6];
set_location_assignment PIN_W11  -to dot_col_1[7];

# set seven segment display


```
:::


## module

### `0.遊戲本體`

### `1.除頻器`

### `2.keypad`

```verilog
`define TimeExpire_KEY 32'd250000
module Check_Keypad (
    input clk,
    input rst,
    input [3:0] keypad_col,
    output reg [3:0] keypad_row,
    output reg [3:0] keypad_buffer
);
    reg [31:0] keypad_delay;

    always @(posedge clk or negedge rst) begin
        if (!rst) begin
            keypad_row <= 4'b1110;
            keypad_buffer <= 4'b0000;
            keypad_delay <= 31'd0;
        end 
        else begin
            if (keypad_delay == `TimeExpire_KEY) begin
                keypad_delay <= 31'd0;
                case ({keypad_row, keypad_col})
                    8'b1101_0111 : keypad_buffer <= 4'ha; //move right 1
                    8'b1011_1011 : keypad_buffer <= 4'h3; //rotate
                    8'b1011_0111 : keypad_buffer <= 4'hb; //move down 1
                    8'b0111_0111 : keypad_buffer <= 4'hf; //move left 1
                    default : keypad_buffer <= keypad_buffer;
                endcase
                case (keypad_row) //refresh
                    4'b1110 : keypad_row <= 4'b1101;
                    4'b1101 : keypad_row <= 4'b1011; 
                    4'b1011 : keypad_row <= 4'b0111; 
                    4'b0111 : keypad_row <= 4'b1110;  
                    default : keypad_row <= 4'b1110;
                endcase
            end 
            else begin
                keypad_delay <= keypad_delay + 1'b1;
            end
        end
    end
    
endmodule 
```

### `3.生成方塊` 

### `4.方塊掉落`

### `5.控制方塊（左右下 旋轉`

### `6.消除連線`

### `7.計分器` 

### `8.seven segment display`

### `9.dot matrix display`