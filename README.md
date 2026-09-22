# Financial Risk Propensity Study System (.NET / WPF)

## Overview
An interactive desktop application built in C# and WPF to conduct behavioral economics experiments[cite: 2]. The application simulates financial decision-making under time pressure, forcing participants to choose between guaranteed outcomes and risky financial options[cite: 2]. It measures risk propensity, tracks changes in participant capital, and collects demographic and psychological data[cite: 2].

## Key Features
* **Participant Profiling**: Collects initial demographic data (age, gender, field of study) and self-assessed psychological indicators (stress management, perceived wealth)[cite: 2].
* **Real-Time Financial Decision Simulation**: Presents sequential choices between sure gains/losses and probabilistic alternatives[cite: 2].
* **Time Pressure & Penalties**: Integrates a dynamic countdown timer for each question; failing to answer within the limit results in a capital penalty[cite: 2].
* **Dynamic Capital Tracking**: Real-time capital adjustment based on chosen decisions and time performance[cite: 2].
* **Data Persistence**: Automatically exports participant responses, reaction times, and final capital scores to structured JSON format (`wynik.json`)[cite: 2].
* **Custom Exception Handling**: Strong input validation ensures dataset integrity prior to experiment initiation[cite: 2].

## System Architecture & Class Structure

### 1. Presentation & Life Cycle (`MainWindow` / `QuestionWindow`)
* `App`: Application lifecyle configuration[cite: 2].
* `MainWindow`: Form interface for participant registration, input validation, and model instantiation[cite: 2].
* `QuestionWindow`: Core experimental interface controlling countdown timers (`DispatcherTimer`), question sequencing, and JSON output generation[cite: 2].

### 2. Core Domain Model & Logic
* `Participant`: Data model holding demographic attributes, dynamic capital state, and auto-generated `Guid`[cite: 2].
* `ParticipantException`: Custom exception class handling validation errors during onboarding[cite: 2].
* `Question` (Abstract): Base template defining time limits, question IDs, and abstract/virtual methods (`ApplyEffect`, `GetQuestionType`)[cite: 2].
* `RiskQuestion`: Inherits from `Question`; implements capital modification logic based on decision options[cite: 2].
* `QuestionOption`: Holds choice labels and respective capital changes[cite: 2].
* `Storage` (Static): JSON serialization engine for experimental results[cite: 2].

## Tech Stack
* **Language**: C# (.NET)[cite: 2]
* **Framework**: Windows Presentation Foundation (WPF)[cite: 2]
* **Data Format**: JSON[cite: 2]
* **Design Patterns**: Object-Oriented Programming (Inheritance, Abstraction, Encapsulation, Custom Exceptions)[cite: 2]

## Authors & Roles
* **Marcin Różalski** – Core Application Logic & Architecture Implementation[cite: 2]
* **Viktoria Toman** – Graphical User Interface (GUI / XAML)[cite: 2]
* **Natalia Grabowska** – Project Documentation & Analysis[cite: 2]

---
*Developed as part of Object-Oriented Programming Coursework (Academic Year 2025/2026).*[cite: 2]
