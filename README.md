# Financial Risk Propensity Study System (.NET / WPF)

## Overview
An interactive desktop application built in C# and WPF to conduct behavioral economics experiments. The application simulates financial decision-making under time pressure, forcing participants to choose between guaranteed outcomes and risky financial options. It measures risk propensity, tracks changes in participant capital, and collects demographic and psychological data.

## Key Features
* **Participant Profiling**: Collects initial demographic data (age, gender, field of study) and self-assessed psychological indicators (stress management, perceived wealth).
* **Real-Time Financial Decision Simulation**: Presents sequential choices between sure gains/losses and probabilistic alternatives.
* **Time Pressure & Penalties**: Integrates a dynamic countdown timer for each question; failing to answer within the limit results in a capital penalty.
* **Dynamic Capital Tracking**: Real-time capital adjustment based on chosen decisions and time performance.
* **Data Persistence**: Automatically exports participant responses, reaction times, and final capital scores to structured JSON format (`wynik.json`).
* **Custom Exception Handling**: Strong input validation ensures dataset integrity prior to experiment initiation.

## System Architecture & Class Structure

### 1. Presentation & Life Cycle (`MainWindow` / `QuestionWindow`)
* `App`: Application lifecycle configuration.
* `MainWindow`: Form interface for participant registration, input validation, and model instantiation.
* `QuestionWindow`: Core experimental interface controlling countdown timers (`DispatcherTimer`), question sequencing, and JSON output generation.

### 2. Core Domain Model & Logic
* `Participant`: Data model holding demographic attributes, dynamic capital state, and auto-generated `Guid`.
* `ParticipantException`: Custom exception class handling validation errors during onboarding.
* `Question` (Abstract): Base template defining time limits, question IDs, and abstract/virtual methods (`ApplyEffect`, `GetQuestionType`).
* `RiskQuestion`: Inherits from `Question`; implements capital modification logic based on decision options.
* `QuestionOption`: Holds choice labels and respective capital changes.
* `Storage` (Static): JSON serialization engine for experimental results.

## Tech Stack
* **Language**: C# (.NET)
* **Framework**: Windows Presentation Foundation (WPF)
* **Data Format**: JSON
* **Design Patterns**: Object-Oriented Programming (Inheritance, Abstraction, Encapsulation, Custom Exceptions)

## Authors & Roles
* **Marcin Różalski** – Core Application Logic & Architecture Implementation
* **Viktoria Toman** – Graphical User Interface (GUI / XAML)
* **Natalia Grabowska** – Project Documentation & Analysis

---
*Developed as part of Object-Oriented Programming Coursework (Academic Year 2025/2026).*
