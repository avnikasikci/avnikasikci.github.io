---
title: Computer System Operation
layout: postByComputer
author: Avni Kaşıkçı
date: '2020-10-22 03:02:32'
thumbnail: "/assets/img/posts/hello.jpg"
category:
- computer
- System-Operation
summary: Computer-System-Operation
keywords: Computer-System-Operation
permalink: "/ComputerEngineer/System-Operation"
categories:
- computer
- System-Operation
---

# Computer System Operation # 
* **I/O on devices and CPU  with run work.**
 
* **Each device controller is responsible for controlling a particular type of device**
 
* **Each device controller on have a local buffer**
* For example, you have connected a printer, this article has a memory unit on it.This memory unit is called the local buffer.
 
* **CPU, moves data bi-directionally between main memory and local buffers**
 
* **I / O Processing takes place from the device to the controller's local buffer memory.**

*  **The device controller informs the CPU that it has completed its operation by causing an interrupt.**



<img class="card-img-top" src="/assets/img/posts/Computer-system-Operaiton.png">






# Common Functions of Interrupts #
**Have you ever heard of "atom commend"?**

There is an expression called atom command in processor architecture.In fact, these cuts are atomic commands.Control of interrupts is sent to the interrupt service routine via the interrupt vector.In the movement of the mouse, for example, the CPU pauses the work it is doing and moves the mouse then continue from where it left off. When a vector is mentioned, a programmer's thought should not come with a vector concept in physics. It is a sequence in terms of computer science. We keep the vectors in the form of a series.If an interrupt occurs, its purpose is for the processor to respond and handle this interrupt. More than one interrupt can occur at the same time.

There is a service that manages the order of these interrupts. This service determines which service should first send to the processor.
The interrupt architecture must save the address of the interrupt instruction the operating system is prone to interrupt.

A trap or exception is a software-based interrupt, a software-generated interrupt caused by an error or user request.
