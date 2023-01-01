//COUNTER

module counter32bit(clk,rst,m,count);
input clk,rst,m;
output reg[31:0]count;
always@(posedge clk or negedge rst)
begin
if(!rst)
count=0;
else if(m)
count=count-1;
else
Count=count+1;
end
endmodule
  
  
module counter_test;
reg clk,rst,m;
wire [31:0]count;
initial
begin
clk=0;
rst=0;
#25;
rst=1;
end
initial
begin
m=1;
#600 m=0;
rst=1;#500 m=0;
end
counter32bit counter32bit1(clk,rst,m,count);
always #5 clk=-clk;
initial
#1400 $finish;
endmodule


read_libs {/home/install/FOUNDRY/digital/45nn/dig/lib/slow.lib}
set_db / .lef Library { /hone/install/FOUNDRY/digital/45mm/dig/lef/gsclib045 tech_lef /home/install/FOUNDRY/digital/dig/lef/gsclib045 macro_lef }
set DESIGN counter32bit
read_hdl "counter.v"
elaborate $DESIGN
check_design -unresolved
read_sdc constraints.sdc
set_db syn_generic_effort medium
set_db syn_map_effort medium
set_db syn_opt_effort medium
syn_generic
syn_map
syn_opt
report_area > area.rpt
report_power > power.rpt
report_gates > gates.rpt
report_timing > timing.rpt
write_hdl > netlist.v
write_sdc > block.sdc
gui_show
