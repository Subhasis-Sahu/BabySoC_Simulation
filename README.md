# BabySoC_Simulation
 Files required for BabySoC Simulation

* src/module - contains all RTL files and testbench.v used for simulating our BabySoC design.
* src/include - contains RTL files used in `include define in  main RTL files in src/module.


* To perform Functional Simulation :
  
  * cd `BabySoC_Simulation`
  * `iverilog -o ./pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module/`
    
* To perform GLS :
  
  * cd `BabySoC_Simulation`
  * `iverilog -DFUNCTIONAL -DUNIT_DELAY=#1 -DPOST_SYNTH_SIM -o ./post_synth_sim.out ./src/module/testbench.v -I ./src/include -I ./src/module -I ./src/gls_model -I ./src/`
  * `./post_synth_sim.out`
  * `gtkwave post_synth_sim.vcd`
