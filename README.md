# KADARIVENU_RISC-V_WEEK-5
OpenROAD Flow Setup and Floorplan + Placement
Here’s a **professional and detailed README.md** you can upload to your **GitHub repository** for your **Week 5 OpenROAD Flow Setup and Floorplan + Placement** task.

---

# 🧠 Week 5 Task – OpenROAD Flow Setup and Floorplan + Placement

### 📘 Objective

The purpose of this task is to set up the **OpenROAD Flow Scripts** environment and execute the **Floorplan** and **Placement** stages of the VLSI physical design flow.
This week marks the transition from **SPICE-level transistor simulation (Week 4)** to **backend implementation**, where digital logic is transformed into an actual silicon layout.

---

## 🔍 Why This Task Matters

After learning about timing behavior at the transistor level, this task demonstrates how those circuits are **physically implemented on silicon**.
You will explore the **OpenROAD** tool — a leading open-source RTL-to-GDSII flow used in both **academic research** and **industrial applications**.

Through this task, you will gain hands-on understanding of:

* 🧩 **Floorplanning** – defining chip core and die area, applying constraints, and placing macros.
* 🧱 **Placement** – arranging standard cells to minimize delay, congestion, and area.
* ⚙️ How **physical design** decisions directly impact **timing**, **area**, and **manufacturability**.

---

## 📂 Reference Repository

You will refer to the following repository for installation and execution guidance:

🔗 **Reference:** [spatha_vsdhdp (Day 14)](https://github.com/spatha0011/spatha_vsdhdp/blob/main/Day14/README.md)

---

## 🧰 Task Components

### 1️⃣ Install OpenROAD Flow Scripts

Follow these steps to set up the environment:

#### Step 1: Clone the OpenROAD Flow Repository

```bash
git clone https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts.git
cd OpenROAD-flow-scripts
```

#### Step 2: Install Prerequisites

Ensure the following packages are installed:

```bash
sudo apt update
sudo apt install -y build-essential cmake python3 python3-venv python3-pip \
                   git gcc g++ make swig tcl-dev tk-dev libx11-dev libxrender-dev \
                   libx11-xcb-dev libxext-dev libxft-dev libboost-all-dev \
                   libeigen3-dev libspdlog-dev
```

#### Step 3: Build the Flow Environment

```bash
./setup.sh
```

This script will automatically fetch dependencies and build the complete OpenROAD toolchain.

#### Step 4: Verify Installation

After installation, confirm OpenROAD is working:

```bash
cd flow
make
./build/openroad
```

If successful, the **OpenROAD TCL shell** will launch.

📸 *Take a screenshot of this step showing your terminal and username.*

---

### 2️⃣ Execute Floorplan and Placement Stages

Once OpenROAD is set up, proceed with the physical design flow up to placement only.

#### Step 1: Run the Flow

From the `flow/` directory:

```bash
make DESIGN=picorv32a
```

This executes all stages, but for this task, you will analyze results **only up to Floorplan and Placement**.

#### Step 2: Check Logs

The logs are generated in:

```
flow/results/<design_name>/logs/
```

Look for:

* `2_1_floorplan.log`
* `3_1_placement.log`

These confirm successful completion of the two stages.

#### Step 3: Visualize Floorplan and Placement

You can visualize using:

```bash
./build/openroad -gui
```

Then, load the design:

```
source flow/designs/<process>/<design_name>/config.mk
```

and open the `.def` or `.odb` files corresponding to **floorplan** and **placement**.

📸 *Capture screenshots of the floorplan and placement layouts with standard cells visible.*

---

## 📑 Deliverables

### 1. Terminal Snapshots

Include clear screenshots showing:

* Commands executed
* Visible Linux username
* Successful installation and setup messages
* Floorplan and placement completion logs

### 2. Output Images

Add images for:

* **Floorplan view** (core and die boundary)
* **Placement layout** (standard cells placed)

### 3. Summary (Example)

> **Summary:**
> I installed OpenROAD Flow Scripts on Ubuntu 22.04 by following the setup script. After verifying the build, I executed the flow for the `picorv32a` design up to floorplan and placement stages. The core area and die dimensions were generated successfully, and standard cells were placed correctly. The main challenge was resolving dependency errors during setup, which I fixed by installing missing `libx11` and `tk` development packages.

---

## 🧩 Directory Structure Example

```
OpenROAD_Week5/
├── screenshots/
│   ├── openroad_install_success.png
│   ├── floorplan_view.png
│   ├── placement_layout.png
├── logs/
│   ├── 2_1_floorplan.log
│   ├── 3_1_placement.log
├── README.md
└── summary.txt
```

---

## 🧠 Learning Outcomes

By completing this task, you have:

* Installed and configured **OpenROAD Flow Scripts** successfully.
* Executed and verified **Floorplan** and **Placement** stages.
* Gained practical insight into how logic circuits are **physically realized on silicon**.

---

## 📅 Submission Checklist

✅ OpenROAD successfully installed
✅ Floorplan and placement completed
✅ Logs and screenshots attached
✅ Summary provided

---

**Author:** *[Your Name]*
**Course:** *VLSI Physical Design – Week 5*
**Date:** *October 2025*

---

Would you like me to generate a **Markdown file (`README.md`) ready for download** with formatting, emojis, and section highlights (for GitHub display)?
