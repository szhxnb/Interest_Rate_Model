---
layout: default
title: Introduction
nav_order: 1
permalink: /
---

## Motivation

This site has been created to summarize my understanding of Interest Rate Models and summarize into a note for sharing. In the next section, I will be intruducing the model I planned to include in this note. 

However, this note is currently incomplete. Even when it is completed, there will be many more complicated models in real market to suffice the valuation and trading strategy construction. Since they are more advanced version of the models in this note including more nuance to address some corner scenarios, I will only talk about these basic ones as a starter. 

You are welcomed to share any insights and make appropriate corrections. 

## Model Introduction

There are 3 most popular methods to model Interest Rate. With an increasing practicability, they are: 
- Short Rate Models 
- Instantaneous Forward Rate Models 
- Market Models

This notes have the following content to introduce these models. 

Firstly, some basic knowledge needs to be reinforced. 

Then, I wrote a chronicle showing the evolution of Interest Rate Models from the first to the third method. 

Lastly, for each model in the three methods, two things will be discussed: 
- Derivation of the formulas
- Simulation for the stochastic differential equation or implementation for the analytical formula (code is shared) 

## Something also useful but won't be talked about in this note 

- Some other models: 

HoLee, BK for short rate, Black-76 for market model

- Two or more factor models: 

To accomadate one more layer of risk with another factor, but more complicated to calibrate, may be added in the future. 

A brief explanation of the difference between one and two factor short rate models: One-factor $$\to$$ Level, Two-factor $$\to$$ Level + Slope
