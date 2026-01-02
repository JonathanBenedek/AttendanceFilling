# Attendance Filling Script

Automatically fill attendance rows on the **Hilan** system.  
Supports both **Office** and **Home** attendance. You can specify **exact times** or **random times within a range**.

---

## Features

- Fill attendance for **Office** or **Home**
- Specify **exact time** or **time range**
- Easy to use with **fetch + eval**

---

## How To Use

1. **Select the chosen days** on the Hilan interface.  
2. Click **"Selected Days"**.  
3. Open **Developer Tools / Inspect**:  
   - Windows: `Ctrl + Shift + I`  
   - Mac: `Cmd + Option + I`  
4. Copy the relevant script and run it in the console.  
   See the **Examples** section below to see the supported scripts.
---

## Examples

### 1. Office Attendance

```javascript
fetch("https://raw.githubusercontent.com/JonathanBenedek/AttendanceFilling/main/hilan")
  .then(r => r.text())
  .then(code => {
    eval(code);
    start({
      where: "home",
      startTime: { exactTime: "09:11" },
      endTime: { range: ["17:30", "18:30"] },
      days: [1]
    });
  });

```

  ### 2. Home Attendance

```javascript
fetch("https://raw.githubusercontent.com/JonathanBenedek/AttendanceFilling/main/hilan")
  .then(r => r.text())
  .then(code => {
    eval(code);
    start({
      where: "home",
      startTime: { exactTime: "09:11" },
      endTime: { range: ["17:30", "18:30"] },
      days: [1, 2, 3, 4, 5]
    });
  });

```

https://github.com/user-attachments/assets/8b707023-b698-4195-832f-49241999f4b1




