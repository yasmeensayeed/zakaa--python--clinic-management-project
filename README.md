# zakaa--python--clinic-management-project# Clinic Hospital Management System

This repository contains a simple console-based application for managing patients in a clinic or hospital. The system allows you to add patients, view patient details, mark patients as completed, and remove patients from the system.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Code Overview](#code-overview)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The Clinic Hospital Management System is designed to help manage patient information efficiently. This application is written in Python and runs in the console, providing a straightforward way to manage a list of patients with basic operations.

## Features

- **Add Patient:** Add new patients with details such as name, age, gender, and condition.
- **View Patients:** View the list of all patients along with their details.
- **Mark Patient as Completed:** Mark a patient's treatment as completed.
- **Remove Patient:** Remove a patient from the system.

## Installation

To run this application, you need to have Python installed on your machine. You can download Python from [python.org](https://www.python.org/).

Clone the repository:

```bash
git clone https://github.com/yourusername/clinic-hospital-management.git
cd clinic-hospital-management


## Usage
python clinic_hospital.py



## Code Overview
class Patient:
    def __init__(self, name, age, gender, condition):
        self.name = name
        self.age = age
        self.gender = gender
        self.condition = condition
        self.completed = False
class ClinicHospital:
    def __init__(self):
        self.patients = []

    def add_patient(self, name, age, gender, condition):
        patient = Patient(name, age, gender, condition)
        self.patients.append(patient)
        print("Patient added successfully.")

    def view_patients(self):
        if not self.patients:
            print("No patients in the system.")
        else:
            for index, patient in enumerate(self.patients):
                print(f"Index: {index}, Name: {patient.name}, Age: {patient.age}, Gender: {patient.gender}, Condition: {patient.condition}, Completed: {'Yes' if patient.completed else 'No'}")

    def mark_patient_completed(self, index):
        try:
            self.patients[index].completed = True
            print("Patient marked as completed.")
        except IndexError:
            print("Invalid index.")

    def remove_patient(self, index):
        try:
            removed_patient = self.patients.pop(index)
            print(f"{removed_patient.name} removed successfully.")
        except IndexError:
            print("Invalid index.")
def main():
    hospital = ClinicHospital()
    while True:
        print("\nOptions:")
        print("1. Add Patient")
        print("2. View Patients")
        print("3. Mark Patient as Completed")
        print("4. Remove Patient")
        print("5. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            name = input("Enter patient's name: ")
            age = input("Enter patient's age: ")
            gender = input("Enter patient's gender: ")
            condition = input("Enter patient's condition: ")
            hospital.add_patient(name, age, gender, condition)
        elif choice == '2':
            hospital.view_patients()
        elif choice == '3':
            index = int(input("Enter index of patient to mark as completed: "))
            hospital.mark_patient_completed(index)
        elif choice == '4':
            index = int(input("Enter index of patient to remove: "))
            hospital.remove_patient(index)
        elif choice == '5':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please enter a valid option.")

if __name__ == "__main__":
    main()






