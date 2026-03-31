---
title: "64 Bit System Verilog Adder"
excerpt: "Designed and verified a SystemVerilog-based calculator chip capable of performing 64-bit addition<br/><img src='/images/final.png' style='width: 300px;'>"
collection: portfolio
---

# Project Overview

This project was part of a structured onboarding process for [Silicon Jackets](https://siliconjackets.gt/), a chip design club at Georgia tech. This onboarding simulated a real-world chip design workflow, where the goal was to design, verify, and understand the physical implementation of a digital system. The main objective was to build a calculator capable of performing 64-bit unsigned integer addition by combining two 32-bit operations, while also developing familiarity with industry-standard tools. The project was divided into three major components: digital design (RTL development), design verification (testbench and validation), and physical design (understanding synthesis and layout processes).
The workflow demonstrated how collaboration between subteams is important to ensure correctness before fabrication, mirroring industry standards. Throughout the project, emphasis was placed on modular design, clear documentation, and iterative debugging. By the end, the system was not only functionally correct, but also thoroughly tested and analyzed, providing a strong foundation in both hardware design and the broader chip development lifecycle.

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
