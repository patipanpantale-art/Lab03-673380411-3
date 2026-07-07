#  java-shipment-exercise

แบบฝึกหัด Java OOP — ระบบคำนวณค่าขนส่ง Shipment  
วิชา Object-Oriented Programming | ปีการศึกษา 2569

---

## คำอธิบายโจทย์

บริษัทขนส่งแห่งหนึ่งมีรายการ **Shipment** หลายรายการ  
ให้เขียนโปรแกรม Java คำนวณค่าขนส่งตามน้ำหนักและประเภท แล้วแสดงยอดรวม

**กฎการคำนวณ:**

| ประเภท | อัตรา |
|--------|-------|
| STANDARD (มาตรฐาน) | 40 บาท / กิโลกรัม |
| EXPRESS (ด่วน) | 100 บาท / กิโลกรัม |

---

## 📁 ไฟล์ในโปรเจกต์

```
java-shipment-exercise/
├── ShipmentSection1_Exercise.java
├── ShipmentSection2_Exercise.java
├── ShipmentSection3_Exercise.java
├── ShipmentSection4_Exercise.java
├── ExpectedOutput_Section1.md
├── ExpectedOutput_Section2.md
├── ExpectedOutput_Section3.md
├── ExpectedOutput_Section4.md
└── README.md
```

> เฉลยไม่ได้อยู่ใน repo นี้ — อาจารย์จะแจกให้หลังส่งงาน

---

## 🍴 วิธีเริ่มต้น (Fork & Clone)

### Step 1 — Fork repo นี้

กดปุ่ม **Fork** มุมบนขวาของหน้านี้

> Fork แล้ว repo จะไปอยู่ใน GitHub ของตัวเอง เช่น  
> `https://github.com/your-username/java-shipment-exercise`

---

### Step 2 — Clone ลงเครื่อง

```bash
git clone https://github.com/your-username/java-shipment-exercise.git
cd java-shipment-exercise
```

> แทน `your-username` ด้วย GitHub username ของตัวเอง

---

### Step 3 — เปิดไฟล์ที่ได้รับมอบหมาย

อาจารย์จะแจ้งว่าให้ทำ Section ใด (1, 2, 3 หรือ 4)

```
Section 1 → ShipmentSection1_Exercise.java + ExpectedOutput_Section1.md
Section 2 → ShipmentSection2_Exercise.java + ExpectedOutput_Section2.md
Section 3 → ShipmentSection3_Exercise.java + ExpectedOutput_Section3.md
Section 4 → ShipmentSection4_Exercise.java + ExpectedOutput_Section4.md
```

เปิด `ExpectedOutput` ของ Section นั้นไว้คู่กันเสมอ

---

### Step 3.5 — ⚠️ ลบไฟล์ Section อื่นที่ไม่ใช่ของตัวเองออก

> **สำคัญมาก** — หลัง Fork แล้วให้ลบไฟล์ของ Section อื่นออกจาก repo ตัวเองด้วย  
> เพื่อไม่ให้สับสน และป้องกันการส่งงานผิด Section

**ตัวอย่าง: ถ้าได้รับมอบหมาย Section 2**

```bash
# ลบไฟล์ Section อื่นที่ไม่ใช่ของตัวเอง
git rm ShipmentSection1_Exercise.java
git rm ShipmentSection3_Exercise.java
git rm ShipmentSection4_Exercise.java
git rm ExpectedOutput_Section1.md
git rm ExpectedOutput_Section3.md
git rm ExpectedOutput_Section4.md

# Commit การลบ
git commit -m "remove: ลบ Section ที่ไม่ใช่ของตัวเองออก"
git push origin main
```

> เก็บไว้เฉพาะไฟล์ของ Section ตัวเอง + README.md เท่านั้น

**โครงสร้างที่ถูกต้องหลังลบ (ตัวอย่าง Section 2):**
```
java-shipment-exercise/
├── ShipmentSection2_Exercise.java   ← เก็บไว้
├── ExpectedOutput_Section2.md       ← เก็บไว้
└── README.md                        ← เก็บไว้เสมอ
```

---

### Step 4 — แก้ Bug ตาม TODO

แต่ละ Section มี Bug ที่ต่างกัน — แก้ตามลำดับ TODO ที่ระบุในไฟล์

| Section | บริษัท | Bug หลักที่ซ่อนไว้ |
|:-------:|--------|-------------------|
| 1 | SpeedEx Logistics | enum ขาด, parameter สลับ, อัตราสลับ |
| 2 | FlashMove Express | enum ขาด, assignment สลับ, อัตราผิด |
| 3 | RocketShip Thailand | if-condition สลับ, index ผิด |
| 4 | SwiftCargo Co., Ltd. | return ค่าผิด, loop condition ผิด |

---

### Step 5 — Compile และ Run

**ตรวจสอบ Java ก่อน:**
```bash
java -version
javac -version
```
ต้องได้ version 17 ขึ้นไป ถ้ายังไม่มีดาวน์โหลดได้ที่ https://adoptium.net

**Compile และ Run (แทน X ด้วยเลข Section):**
```bash
javac ShipmentSectionX_Exercise.java
java  ShipmentSectionX_Exercise
```

เปรียบเทียบผลลัพธ์กับ `ExpectedOutput_SectionX.md`

---

### Step 6 — Push และส่งงาน

```bash
git add ShipmentSectionX_Exercise.java
git commit -m "fix: แก้ไข TODO Section X เสร็จสมบูรณ์"
git push origin main
```

**ส่ง link repo ให้อาจารย์:**  
`https://github.com/your-username/java-shipment-exercise`

---

## ❗ Error ที่พบบ่อย

| Error | สาเหตุ | ดู TODO |
|-------|--------|--------|
| `error: cannot find symbol` | enum ไม่ครบ | A (Sec 1, 2) |
| `NullPointerException` | ลืม `new ArrayList<>()` | E (Sec 1, 2) |
| ทุกรายการได้ `0.00` | `return 0` แทน `return cost` | A (Sec 4) |
| ตัวเลขสลับ STANDARD/EXPRESS | if-condition ผิด | A (Sec 3) |
| ยอดรวมผิด (น้อยกว่าที่ควร) | loop วนไม่ครบ | C (Sec 3, 4) |
| ไม่มีบรรทัดรายการใดแสดง | `printSummary()` ไม่มี loop | G/D |

---

## ✅ Checklist ก่อนส่ง

- [ ] Fork repo แล้ว
- [ ] Clone ลงเครื่องแล้ว
- [ ] ลบไฟล์ Section อื่นออกแล้ว (เหลือแค่ Section ของตัวเอง)
- [ ] แก้ TODO ครบทุกจุด
- [ ] `javac` ผ่าน ไม่มี error
- [ ] `java` รันได้ ไม่มี Exception
- [ ] ผลลัพธ์ตรงกับ ExpectedOutput ทุกบรรทัด
- [ ] ยอดรวมมี comma เช่น `1,070.00`
- [ ] `git push` ขึ้น GitHub แล้ว
- [ ] ส่ง link repo ให้อาจารย์แล้ว
