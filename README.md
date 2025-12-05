# 📅 Scheduler-ClassAssistant

## 📝 Description

The **Scheduler-ClassAssistant** is a robust tool for creating and optimizing academic timetables. It leverages concepts from **mathematical programming**, such as **genetic algorithms** and **integer methods**, to solve complex resource-allocation and constraint problems.

With an intuitive graphical interface, the system enables easy visualization and adjustment of generated schedules, combining the power of advanced optimization techniques with practical usability.

---

## 🧠 Mathematical Programming & Modeling

The **Scheduler-ClassAssistant** is built upon two major optimization pillars:

---

### 🧬 1. Genetic Algorithms (GA)

Genetic algorithms are inspired by natural selection. In this project, they help find near-optimal solutions for the scheduling allocation problem.

#### 🔹 Main Steps:

1. **🌱 Initial Population**

   * Each solution (individual) is a randomly generated timetable.
   * Chromosomes represent solutions; genes represent elements of the schedule.

2. **📈 Fitness Function**
   Evaluates how suitable a solution is by considering:

   * Scheduling conflicts (e.g., two monitors in the same room).
   * Student preferences.
   * Minimization of idle times.
     The fewer the conflicts and the closer to preferences, the better the score.

3. **🧬 Genetic Operators**

   * **Selection:** Higher-fitness solutions are more likely to reproduce.
   * **Crossover:** Combines sections of two individuals into a new solution.
   * **Mutation:** Introduces small random changes to avoid stagnation.

4. **🔁 Evolution**

   * New generations are created iteratively until a stopping criterion is met (e.g., number of generations or desired fitness).

---

### 🧩 2. Integer Programming Methods

Used for situations requiring stricter, fully deterministic solutions.

#### 🔢 Integer Model

##### 🎯 Decision Variables:

* ( x_{ad} ): 1 if monitor (a) is assigned to course (d); 0 otherwise
* ( y_d ): 1 if course (d) is left without a monitor; 0 otherwise

---

### 🎯 Objective Function

Maximize the total score of assigned monitors by:

* ⭐ Prioritizing monitors with higher average grades
* 🚫 Minimizing the number of courses without an assigned monitor

The result balances academic performance with broad course coverage.

---

### 📏 Constraints

1. **📘 Per Course Allocation**

   * Each course may have at most one monitor assigned.
   * If none is assigned, the course is marked as *unattended*.

2. **👤 Per Monitor Limit**

   * Each monitor can be assigned to at most one course.

3. **💬 Monitor Preferences**

   * A monitor can only be assigned to a course they showed interest in.

4. **🔒 Variable Types**

   * Both ( x_{ad} ) and ( y_d ) are binary (0 or 1).

---

### 📚 Parameters

* ( A ): Set of available monitors
* ( D ): Set of available courses
* ( s_{ad} ): 1 if monitor (a) is willing to monitor course (d); 0 otherwise
* ( N_a ): Average grade of monitor (a), used to prioritize assignments

---

## 💻 How to Use

A **Windows installer** is available here:
👉 [Download Executable](/builds/Scheduler%20Class%20Assistant_0.1.0_x64_en-US.msi)

Example input files:

📘 [Courses](dataset/courses_data.xlsx)
🧑‍🎓 [Students](dataset/students_data.xlsx)

During execution, you can download templates showing how input files must be formatted.
Manual data entry is also supported.

After providing the data:

1. Choose the model
2. Configure parameters (optional)
3. Run the solver 🚀

A results table and execution metrics will be displayed, and you can download outputs in **.xlsx** or **.csv** formats.

---

## 🛠 Development Instructions

If you wish to run the program in a development environment, follow the steps below.

### 📦 Development Requirements

#### 🔹 Backend (Python)

* Python 3.8 or higher
* Install dependencies:

```bash
pip install -r back/requirements.txt
```

#### 🔹 Frontend (Node.js + PNPM)

```bash
cd front
pnpm install
```

---

### ▶️ Running in Development Mode

First generate the Python executables:

```bash
cd back
make
```

Then run the frontend:

```bash
cd front
pnpm run dev
```

---

### 🏗 Building the Project

```bash
cd front
pnpm tauri build
```

---

## 🧰 Technologies & Tools Used

* 🐍 **Python** – core logic and algorithms
* 🧬 **DEAP** – genetic algorithm implementation
* 📐 **SciPy / PuLP** – linear programming solvers
* 🟢 **Node.js + PNPM** – frontend tooling
* 🪟 **Tauri** – desktop application framework
* 🎨 **Tailwind CSS** – responsive UI styling

---

## ⭐ Benefits of the Model

* **⚙ Flexibility** – Combines heuristic (GA) and exact (integer programming) methods
* **🎯 Custom Optimization** – Supports different prioritization criteria
* **📈 Scalability** – Handles large volumes (many classes, teachers, schedules)
* **⚡ Computational Efficiency** – Optimized algorithms for fast convergence

---

## 📜 License

The **Scheduler Class Assistant** is released under the **MIT License**.
We are not responsible for any damages caused by the use of this software.

---

## 👥 Project Members

* Carlos Filipe de Castro Lemos
* Gabriel Barbosa de Oliveira
* Henrique Souza Marques
* João Pedro Matos de Deus
* Lucas Greff Meneses
