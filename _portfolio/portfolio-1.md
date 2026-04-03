---
title: "64 Bit System Verilog Adder"
excerpt: "Designed and verified a SystemVerilog-based calculator chip capable of performing 64-bit addition<br/><img src='/images/final.png' style='width: 300px;'>"
collection: portfolio
---

# Project Overview

This project was part of a structured onboarding process for [Silicon Jackets](https://siliconjackets.gt/), a chip design club at Georgia tech. This onboarding simulated a real-world chip design workflow, where the goal was to design, verify, and understand the physical implementation of a digital system. The main objective was to build a calculator capable of performing 64-bit unsigned integer addition by combining two 32-bit operations, while also developing familiarity with industry-standard tools. The project was divided into three major components: digital design (RTL development), design verification (testbench and validation), and physical design (understanding synthesis and layout processes).
The workflow demonstrated how collaboration between subteams is important to ensure correctness before fabrication, mirroring industry standards. Throughout the project, emphasis was placed on modular design, clear documentation, and iterative debugging. By the end, the system was not only functionally correct, but also thoroughly tested and analyzed, providing a strong foundation in both hardware design and the broader chip development lifecycle.
<br>

# Digital Design

<div style="display: flex; align-items: flex-start; gap: 40px; margin-bottom: 40px;">

  <div style="flex: 1;">
    <p>
      The digital design portion of this projedct focused on implementing the calculator at the RTL level using SystemVerilog. The system was composed of several key modules, including a 32-bit adder, result buffer, a controller, and a top-level integration module. The 32-bit addedr was constructed using a hierarchy of 1-bit full adders connected through generate statements, enabling scalable and efficient operations. The result buffer stored intermediate results and allowed selective placement of data into either half of a 64-bit register.
The controller was implemented as a finate state machine (FSM) that coordinated all operations within the system. It handled reading operands from memory, sequencing lower and upper 32-bit additions, managing carry in and carry out propogation, and writing results back to memory. This required careful attention to control signals, timing, and synchroniztion between modules. The top-level module integrated all components and connected them to a simulalte SRAM interface, enabling full functionality.
A major focus of this phase was desigining clean, synthesizable hardware using practices such as separating combinational and sequantial logic and ensuring proper signal flow. The result was a modular design that accurately performed large-scale arithmetic operations while maintaining clarity and structure.
    </p>
  </div>

  <div style="display: flex; flex-direction: column; gap: 30px;">

  <div style="display: flex; flex-direction: column; align-items: center;">
      <img src="/images/code.png" style="width: 300px; margin-bottom: 10px;">
      <p style="text-align: center;">Code from controller</p>
    </div>

   <div style="display: flex; flex-direction: column; align-items: center;">
      <img src="/images/timing.png" style="width: 300px; margin-bottom: 10px;">
      <p style="text-align: center;">Timing diagram to help debug code</p>
    </div>

  </div>

</div>

# Design Verification

The verification phase ensure that the designed system behaved correctly under a wide range of conditions and parameters before tapeout. This involved developing a comprehensive testbench environment that interacted dwith the design under test (DUT) and validated its functionality through simulation. The testbench included key components suchh as a driver, monitor, scoreboard, and sequence items, each responsible for different aspects of stimulus generation and result checking. <br>
A detailed test plan was created to guide verification efforts, including functional tests, edge case testing, constrained randomized testing, and assertion-based testing. Functional tests verified basic arithmetic operations, while edge case tests ensured correct behavior under boundary conditions such as overflow scenarios. Constrained random testing allowed for broad input coverage without manually writing extensive test cases, improving confidence in the design. <br>
Assertions were used to verify internal behaviors, such as correct carry propagation and proper sequencing of operations, which are not always visible through outputs alone. Coverage analysis tools were used to measure how thoroughly the design was tested, with a target of achieving at least 98% coverage, with my design covering 99.5% of cases. This phase reinforced the importance of rigorous validation and demonstrated how verification plays a critical role in ensuring hardware reliability before physical implementation.
<br>

# Physical Design

<div style="display: flex; align-items: flex-start; gap: 40px; margin-bottom: 40px;">

  <div style="flex: 1;">
    <p>
      The physical design portion introduced the process of transforming RTL into a manufacturable chip layout. While the project did not require full custom layout design, it provided exposure to the key stages involved in physical implementation, including synthesis, placement and routing, and static timing analysis. RTL code is first synthesized into a gate-level netlist, which definess the logic gates and their interconnections, and is then used to generate a physical layout of thechip.
      Key considerations in physical design include power, performance (timing), and area, which must be balanced during optimization. Tools such as Cadence Genus and Innovus are used to automate these processes, while static timing analysis ensures that signal propagation delays meet required clock constraints. The project also introduced concepts such as clock distribution, routing congestion, and design rule checking, all of which are critical for producing a functional and efficient chip.
Additionally, scripting and debugging workflows were emphasized, highlighting how automation is used to manage complex design flows. This exposure provided insight into how high-level hardware descriptions are ultimately translated into real silicon, reinforcing the connection between digital design decisions and their physical consequences.
    </p>
  </div>

  <div style="display: flex; flex-direction: column; gap: 30px;">

  <div style="display: flex; flex-direction: column; align-items: center;">
      <img src="/images/slack.png" style="width: 300px; margin-bottom: 10px;">
      <p style="text-align: center;">Static timing analysis shows no negative slack</p>
    </div>

   <div style="display: flex; flex-direction: column; align-items: center;">
      <img src="/images/debug.png" style="width: 300px; margin-bottom: 10px;">
      <p style="text-align: center;">Chip mid-debugging process</p>
    </div>

  </div>

</div>

# What I Gained

During this six-week onboarding project, I learned about Digital Design, Design Verification, and Physical Design, broadening my total knowledge on the subject. However, I believe the most important part of this project to me was the fact that it opened my eyes to digital design. Unlike typical computer science (which I'm more accustomed to), digital design requires more attention to detail and more awareness of what you're actually making. Because this will take up real space on real chips, everything must be intentional and you can't take shortcuts. This philosophy is very important to me, and it is why I believe digital design is the career choice for me.
