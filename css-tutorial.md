# ใบงานการทดลอง: พื้นฐานการจัดการรูปแบบเว็บไซต์ด้วย CSS
[](#การทดลองที่-1-ทำความรู้จักกับ-css)
## การทดลองที่ 1: ทำความรู้จักกับ CSS

### 1.1 วิธีการใช้งาน CSS
CSS สามารถใช้งานได้ 3 วิธี:

1. **Inline CSS**:
```html
<p style="color: blue; font-size: 16px;">ข้อความสีน้ำเงิน</p>
```

2. **Internal CSS**:
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
```

3. **External CSS**:
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

### ตัวอย่างการใช้งาน: การสร้างปุ่มสไตล์ต่างๆ

```html
<!-- ไฟล์ index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>ตัวอย่างปุ่ม CSS</title>
    <!-- Internal CSS -->
    <style>
        .btn-primary {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
    <!-- External CSS -->
    <link rel="stylesheet" href="css/buttons.css">
</head>
<body>
    <!-- Inline CSS -->
    <button style="background-color: #dc3545; color: white; padding: 10px 20px;">ปุ่มแบบ Inline</button>
    
    <!-- Internal CSS -->
    <button class="btn-primary">ปุ่มแบบ Internal</button>
    
    <!-- External CSS -->
    <button class="btn-success">ปุ่มแบบ External</button>
</body>
</html>
```

```css
/* สร้างไฟล์ buttons.css ในโฟลเดอร์ css */
.btn-success {
    background-color: #28a745;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
```
[](#การทดลองที่-2-selectors-ใน-CSS)
## การทดลองที่ 2: Selectors ใน CSS
CSS Selector คือวิธีการระบุหรือเลือกองค์ประกอบ (elements) ที่เราต้องการจัดรูปแบบใน HTML โดยมีประเภทหลัก ๆ ดังนี้:

1. **Element Selector** - เลือกโดยใช้ชื่อ element
```css
p { color: red; }  /* เลือกทุก <p> elements */
h1 { color: blue; }  /* เลือกทุก <h1> elements */
```

2. **Class Selector** - เลือกโดยใช้ชื่อ class (ขึ้นต้นด้วย .)
```css
.menu { color: green; }  /* เลือก elements ที่มี class="menu" */
.highlight { background: yellow; }
```

3. **ID Selector** - เลือกโดยใช้ ID (ขึ้นต้นด้วย #)
```css
#header { background: black; }  /* เลือก element ที่มี id="header" */
#logo { width: 100px; }
```

4. **Descendant Selector** - เลือก elements ที่เป็นลูกหลาน
```css
div p { color: blue; }  /* เลือก <p> ที่อยู่ภายใน <div> */
```

5. **Child Selector** - เลือก elements ที่เป็นลูกโดยตรง (>)
```css
div > p { color: red; }  /* เลือก <p> ที่เป็นลูกโดยตรงของ <div> */
```

6. **Pseudo-class** - เลือกสถานะพิเศษ
```css
a:hover { color: red; }  /* เมื่อเมาส์ชี้ */
input:focus { border: blue; }  /* เมื่อได้รับการโฟกัส */
```

7. **Multiple Selector** - เลือกหลายอย่างพร้อมกัน
```css
h1, h2, h3 { color: purple; }
```

8. **Universal Selector** - เลือกทุก elements (*)
```css
* { margin: 0; padding: 0; }
```

9. **Attribute Selector** - เลือกตาม attribute
```css
input[type="text"] { border: 1px solid gray; }
```

10. **Adjacent Sibling Selector** - เลือกธาตุที่อยู่ถัดไป (+)
```css
h1 + p { margin-top: 20px; }
```

ความสำคัญของ Selector:
- ช่วยให้เราสามารถกำหนดสไตล์ให้กับ elements ที่ต้องการได้อย่างเฉพาะเจาะจง
- ช่วยในการจัดการและบำรุงรักษาโค้ด CSS
- ทำให้สามารถสร้างรูปแบบที่ซับซ้อนได้
- ช่วยลดการเขียนโค้ดซ้ำซ้อน
  
### 2.1 ประเภทของ Selectors
```css
/* Element Selector */
p {
    color: blue;
}

/* Class Selector */
.highlight {
    background-color: yellow;
}

/* ID Selector */
#header {
    font-size: 24px;
}

/* Descendant Selector */
div p {
    margin: 10px;
}

/* Child Selector */
div > p {
    padding: 5px;
}
```

### ตัวอย่างการใช้งาน: การสร้างเมนูนำทาง

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        /* การใช้ Element Selector */
        nav {
            background-color: #333;
            padding: 15px;
        }

        /* การใช้ Descendant Selector */
        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }

        /* การใช้ Child Selector */
        nav > ul > li {
            margin: 0 10px;
        }

        /* การใช้ Class Selector */
        .menu-item {
            color: white;
            text-decoration: none;
            padding: 5px 10px;
        }

        /* การใช้ Pseudo-class */
        .menu-item:hover {
            background-color: #555;
            border-radius: 3px;
        }

        /* การใช้ ID Selector */
        #active {
            background-color: #007bff;
            border-radius: 3px;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item" id="active">หน้าแรก</a></li>
            <li><a href="#" class="menu-item">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</body>
</html>
```
### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. แก้ไขให้เมนูถูกเลือกที่ สินค้า
3. เปลี่ยนสีพื้นหลังของเมนู
### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gallery App</title>
  <link rel="stylesheet" href="styles.css"> <!-- ใช้ External CSS -->
</head>
<body>

  <!-- แถบนำทาง -->
  <nav>
    <a href="index.html">หน้าแรก</a>
    <a href="index.html"class="active">สินค้า</a>
    <a href="pages/about.html">เกี่ยวกับ</a>
    <a href="pages/contact.html">ติดต่อ</a>
    <a href="files/document.pdf" download>Download Document</a>
  </nav>

  <button class="back-btn" onclick="history.back()">Back</button>

  <!-- แกลเลอรี่สินค้า -->
  <div class="gallery">
    <div class="gallery-item" onclick="showDialog('images/products/product1.jpg', 'Product 1')">
      <img src="images/products/product1.jpg" alt="Product 1">
      <p>Product 1</p>
    </div>
    <div class="gallery-item" onclick="showDialog('images/products/product2.png', 'Product 2')">
      <img src="images/products/product2.png" alt="Product 2">
      <p>Product 2</p>
    </div>
    <div class="gallery-item" onclick="showDialog('images/products/product3.jpg', 'Product 3')">
      <img src="images/products/product3.jpg" alt="Product 3">
      <p>Product 3</p>
    </div>
    <div class="gallery-item" onclick="showDialog('images/products/product4.jpg', 'Product 4')">
      <img src="images/products/product4.jpg" alt="Product 4">
      <p>Product 4</p>
    </div>
  </div>

  <!-- Popup Dialog -->
  <div id="dialog" class="dialog">
    <div class="dialog-content">
      <img id="dialog-image" src="" alt="">
      <p id="dialog-description"></p>
      <button class="close-btn" onclick="closeDialog()">Close</button>
    </div>
  </div>

  <script>
    function showDialog(imageSrc, description) {
      document.getElementById('dialog-image').src = imageSrc;
      document.getElementById('dialog-description').textContent = description;
      document.getElementById('dialog').style.display = 'flex';
    }

    function closeDialog() {
      document.getElementById('dialog').style.display = 'none';
    }
  </script>

</body>
</html>
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

![Screenshot 2025-02-11 220813](https://github.com/user-attachments/assets/ab4822dd-3cc3-4d50-a39c-c500bc166ef4)


[](#การทดลองที่-3-การจัดการสีและพื้นหลัง)
## การทดลองที่ 3: การจัดการสีและพื้นหลัง

### 3.1 การกำหนดสีและพื้นหลัง
```css
/* สีพื้นฐาน */
color: red;
color: #FF0000;
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5);

/* พื้นหลัง */
background-color: #f0f0f0;
background-image: url('image.jpg');
background-size: cover;
```

### ตัวอย่างการใช้งาน: การสร้างการ์ดสินค้า

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .product-card {
            width: 300px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            background-color: white;
        }

        .product-image {
            width: 100%;
            height: 200px;
            background-image: url('product.jpg');
            background-size: cover;
            background-position: center;
        }

        .product-info {
            padding: 15px;
        }

        .product-title {
            color: #333;
            font-size: 18px;
            margin-bottom: 10px;
        }

        .product-price {
            color: #007bff;
            font-size: 24px;
            font-weight: bold;
        }

        .product-description {
            color: #666;
            font-size: 14px;
            line-height: 1.5;
        }

        .product-button {
            display: block;
            background: linear-gradient(to right, #007bff, #0056b3);
            color: white;
            text-align: center;
            padding: 10px;
            text-decoration: none;
            margin-top: 15px;
            border-radius: 4px;
        }

        .product-button:hover {
            background: linear-gradient(to right, #0056b3, #003980);
        }
    </style>
</head>
<body>
    <div class="product-card">
        <div class="product-image"></div>
        <div class="product-info">
            <h2 class="product-title">สินค้าตัวอย่าง</h2>
            <p class="product-price">฿1,999</p>
            <p class="product-description">
                รายละเอียดสินค้าตัวอย่าง ที่มีความน่าสนใจและน่าใช้งาน
            </p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. แก้ไขให้แสดงรูปสินค้า โดยให้รูปสินค้าเก็บอยู่ในโฟลเดอร์ images
3. เพิ่มเติมให้มี card แสดงข้อมูลสินค้า 4 รูป

### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Product Gallery</title>
  <link rel="stylesheet" href="styles.css"> <!-- ใช้ External CSS -->
</head>
<body>

  <!-- แถบนำทาง -->
  <nav>
    <a href="index.html">หน้าแรก</a>
    <a href="index.html" class="active">สินค้า</a>
    <a href="pages/about.html">เกี่ยวกับ</a>
    <a href="pages/contact.html">ติดต่อ</a>
    <a href="files/document.pdf" download>Download Document</a>
  </nav>

  <button class="back-btn" onclick="history.back()">Back</button>

  <!-- รายการสินค้า -->
  <div class="product-container">
    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product1.jpg" alt="Product 1">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 1</h2>
        <p class="product-price">฿1,999</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product2.png" alt="Product 2">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 2</h2>
        <p class="product-price">฿1,599</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product3.jpg" alt="Product 3">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 3</h2>
        <p class="product-price">฿999</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product4.jpg" alt="Product 4">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 4</h2>
        <p class="product-price">฿1,299</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>
  </div>

</body>
</html>

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

[](#การทดลองที่-4-การจัดการขนาดและระยะห่าง)
## การทดลองที่ 4: การจัดการขนาดและระยะห่าง
![Screenshot 2025-02-11 224815](https://github.com/user-attachments/assets/c1355d01-6ac6-435f-b7ba-872b8d49c6f9)

### 4.1 หน่วยวัดและ Box Model
```css
/* หน่วยวัด */
width: 100px;
width: 50%;
font-size: 1.2rem;
height: 100vh;

/* Box Model */
padding: 10px;
margin: 15px;
border: 1px solid black;
```

### ตัวอย่างการใช้งาน: การสร้างส่วนแสดงสถิติ

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .stats-container {
            display: flex;
            justify-content: space-around;
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .stat-box {
            flex: 1;
            margin: 0 15px;
            padding: 2rem;
            text-align: center;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #007bff;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .stats-container {
                flex-direction: column;
            }

            .stat-box {
                margin: 1rem 0;
            }
        }
    </style>
</head>
<body>
    <div class="stats-container">
        <div class="stat-box">
            <div class="stat-number">1,234</div>
            <div class="stat-label">ผู้ใช้งาน</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">5.6K</div>
            <div class="stat-label">ยอดขาย</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">98%</div>
            <div class="stat-label">ความพึงพอใจ</div>
        </div>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่ง ขนาดต่าง ๆ ของ Box model, ขนาดและฟอนต์ตัวหนังสือ, สี


### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Product Gallery</title>
  <link rel="stylesheet" href="styles.css"> <!-- ใช้ External CSS -->
</head>
<body>

  <!-- แถบนำทาง -->
  <nav>
    <a href="index.html">หน้าแรก</a>
    <a href="index.html" class="active">สินค้า</a>
    <a href="pages/about.html">เกี่ยวกับ</a>
    <a href="pages/contact.html">ติดต่อ</a>
    <a href="files/document.pdf" download>Download Document</a>
  </nav>

  <button class="back-btn" onclick="history.back()">Back</button>

  <!-- รายการสินค้า -->
  <div class="product-container">
    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product1.jpg" alt="Product 1">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 1</h2>
        <p class="product-price">฿1,999</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product2.png" alt="Product 2">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 2</h2>
        <p class="product-price">฿1,599</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product3.jpg" alt="Product 3">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 3</h2>
        <p class="product-price">฿999</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product4.jpg" alt="Product 4">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 4</h2>
        <p class="product-price">฿1,299</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
</body>
</html>

```
```css
/* ตั้งค่าพื้นฐาน */
body {
    font-family: "Poppins", sans-serif;
    margin: 0;
    padding: 20px;
    background-color: #f8f9fa;
}

/* สไตล์เมนูนำทาง */
nav {
    display: flex;
    justify-content: center;
    background: #6c5ce7;
    padding: 15px;
    border-radius: 10px;
}

nav a {
    color: white;
    text-decoration: none;
    font-size: 18px;
    font-weight: 500;
    padding: 12px 20px;
    border-radius: 8px;
    transition: background 0.3s ease-in-out;
}

nav a:hover {
    background: #a29bfe;
}

nav a.active {
    background: white;
    color: #6c5ce7;
}

/* ปุ่มย้อนกลับ */
.back-btn {
    margin: 20px auto;
    display: block;
    padding: 10px 15px;
    font-size: 16px;
    background: #ff7675;
    color: white;
    border-radius: 5px;
    border: none;
    cursor: pointer;
    transition: 0.3s;
}

.back-btn:hover {
    background: #d63031;
}

/* สไตล์รายการสินค้า */
.product-container {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
    margin-top: 30px;
}

/* การ์ดสินค้า */
.product-card {
    width: 320px;
    border-radius: 12px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    background-color: white;
    text-align: center;
    padding: 20px;
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
}

/* รูปภาพสินค้า */
.product-image img {
    width: 100%;
    height: 220px;
    object-fit: cover;
    border-radius: 8px;
}

/* ข้อความสินค้า */
.product-title {
    color: #333;
    font-size: 22px;
    font-weight: bold;
    margin: 15px 0 8px;
}

.product-price {
    color: #0984e3;
    font-size: 20px;
    font-weight: bold;
}

.product-description {
    color: #636e72;
    font-size: 15px;
    line-height: 1.6;
    margin-bottom: 15px;
}
.product-button:hover {
    background: linear-gradient(to right, #574b90, #0652dd);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![Screenshot 2025-02-11 225611](https://github.com/user-attachments/assets/a18f2a09-4769-4091-9605-7f28295b36fb)

[](#การทดลองที่-5-การจัดการข้อความและฟอนต์)
## การทดลองที่ 5: การจัดการข้อความและฟอนต์

### 5.1 การจัดการข้อความและฟอนต์
```css
/* การจัดการข้อความ */
text-align: center;
text-decoration: none;
text-transform: uppercase;
line-height: 1.5;

/* การจัดการฟอนต์ */
font-family: 'Arial', sans-serif;
font-size: 16px;
font-weight: bold;
```

### ตัวอย่างการใช้งาน: การสร้างบทความบล็อก

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .blog-post {
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1rem;
            font-family: 'Sarabun', sans-serif;
        }

        .post-header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .post-title {
            font-size: 2.5rem;
            color: #333;
            margin-bottom: 0.5rem;
            line-height: 1.2;
        }

        .post-meta {
            color: #666;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .post-content {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #444;
        }

        .post-content p {
            margin-bottom: 1.5rem;
        }

        .post-content h2 {
            font-size: 1.8rem;
            color: #333;
            margin: 2rem 0 1rem;
        }

        blockquote {
            font-style: italic;
            border-left: 4px solid #007bff;
            margin: 1.5rem 0;
            padding-left: 1rem;
            color: #555;
        }

        @media (max-width: 768px) {
            .post-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <article class="blog-post">
        <header class="post-header">
            <h1 class="post-title">วิธีการเขียนบทความที่น่าสนใจ</h1>
            <div class="post-meta">โพสต์เมื่อ 1 มกราคม 2025 | โดย ผู้เขียน</div>
        </header>
        
        <div class="post-content">
            <p>เนื้อหาบทความที่ดีควรมีความน่าสนใจและเป็นประโยชน์ต่อผู้อ่าน การเขียนบทความให้น่าอ่านนั้นมีหลักการสำคัญหลายประการ</p>

            <h2>1. การเลือกหัวข้อที่น่าสนใจ</h2>
            <p>หัวข้อที่ดีควรตรงกับความสนใจของกลุ่มเป้าหมาย และมีประโยชน์ต่อผู้อ่าน</p>

            <blockquote>
                "การเขียนที่ดีไม่ได้เกิดจากพรสวรรค์เพียงอย่างเดียว แต่เกิดจากการฝึกฝนอย่างสม่ำเสมอ"
            </blockquote>

            <h2>2. การจัดโครงสร้างเนื้อหา</h2>
            <p>เนื้อหาที่ดีควรมีการจัดลำดับที่เป็นระบบ เข้าใจง่าย และมีความต่อเนื่อง</p>
        </div>
    </article>
</body>
</html>
```
### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งรูปแบบ สีและขนาด font

### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Product Gallery</title>
  <link rel="stylesheet" href="styles.css"> <!-- ใช้ External CSS -->
</head>
<body>

  <!-- แถบนำทาง -->
  <nav>
    <a href="index.html">หน้าแรก</a>
    <a href="index.html" class="active">สินค้า</a>
    <a href="pages/about.html">เกี่ยวกับ</a>
    <a href="pages/contact.html">ติดต่อ</a>
    <a href="files/document.pdf" download>Download Document</a>
  </nav>

  <button class="back-btn" onclick="history.back()">Back</button>

  <!-- รายการสินค้า -->
  <div class="product-container">
    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product1.jpg" alt="Product 1">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 1</h2>
        <p class="product-price">฿1,999</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product2.png" alt="Product 2">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 2</h2>
        <p class="product-price">฿1,599</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product3.jpg" alt="Product 3">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 3</h2>
        <p class="product-price">฿999</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product4.jpg" alt="Product 4">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 4</h2>
        <p class="product-price">฿1,299</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
      </div>
</body>
</html>

```
```css
/* ตั้งค่าพื้นฐาน */
body {
    font-family: "Poppins", sans-serif;
    margin: 0;
    padding: 20px;
    background-color: #f8f9fa;
}

/* สไตล์เมนูนำทาง */
nav {
    display: flex;
    justify-content: center;
    background: #6c5ce7;
    padding: 15px;
    border-radius: 10px;
}

nav a {
    color: white;
    text-decoration: none;
    font-size: 18px;
    font-weight: 500;
    padding: 12px 20px;
    border-radius: 8px;
    transition: background 0.3s ease-in-out;
}

nav a:hover {
    background: #a29bfe;
}

nav a.active {
    background: white;
    color: #6c5ce7;
}

/* ปุ่มย้อนกลับ */
.back-btn {
    margin: 20px auto;
    display: block;
    padding: 10px 15px;
    font-size: 16px;
    background: #ff7675;
    color: white;
    border-radius: 5px;
    border: none;
    cursor: pointer;
    transition: 0.3s;
}

.back-btn:hover {
    background: #d63031;
}

/* สไตล์รายการสินค้า */
.product-container {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
    margin-top: 30px;
}

/* การ์ดสินค้า */
.product-card {
    width: 320px;
    border-radius: 12px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    background-color: white;
    text-align: center;
    padding: 20px;
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
}

/* รูปภาพสินค้า */
.product-image img {
    width: 100%;
    height: 220px;
    object-fit: cover;
    border-radius: 10px;
}

/* ข้อความสินค้า */
.product-title {
    color: #333;
    font-size: 24px;
    font-weight: bold;
    margin: 15px 0 8px;
}

.product-price {
    color: #00983a;
    font-size: 25px;
    font-weight: bold;
}

.product-description {
    color: #00bbff;
    font-size: 20px;
    line-height: 1.6;
    margin-bottom: 15px;
}

.product-button:hover {
    background: linear-gradient(to right, #574b90, #0652dd);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![Screenshot 2025-02-11 230846](https://github.com/user-attachments/assets/ad7a73c7-fed9-48b4-8c23-736054215c13)

[](#การทดลองที่-6-Layout-และการจัดวางอิลิเมนต์)
## การทดลองที่ 6: Layout และการจัดวางอิลิเมนต์

### 6.1 การจัดวางด้วย Flexbox และ Grid

```css
/* Flexbox */
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Grid */
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### ตัวอย่างการใช้งาน: การสร้างหน้าแสดงสินค้าแบบ Grid

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .product-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .product-card:hover {
            transform: translateY(-5px);
        }

        .product-image {
            width: 100%;
            height: 200px;
            background-color: #f5f5f5;
            background-size: cover;
            background-position: center;
        }

        .product-details {
            padding: 15px;
        }

        .product-title {
            font-size: 1.1rem;
            margin: 0 0 10px 0;
            color: #333;
        }

        .product-price {
            font-size: 1.2rem;
            color: #007bff;
            font-weight: bold;
        }

        .product-action {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
        }

        .add-to-cart {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
        }

        .add-to-cart:hover {
            background-color: #0056b3;
        }

        @media (max-width: 768px) {
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="product-grid">
        <!-- สินค้าชิ้นที่ 1 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('product1.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สินค้าตัวอย่างที่ 1</h3>
                <div class="product-price">฿1,299</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- สินค้าชิ้นที่ 2 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('product2.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สินค้าตัวอย่างที่ 2</h3>
                <div class="product-price">฿1,499</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- เพิ่มสินค้าอื่นๆ ตามต้องการ -->
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งขนาดแสดงผลสินค้าให้เล็กลง
3. เพ่ิมรูปภาพของสินค้า


### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Product Gallery</title>
  <link rel="stylesheet" href="styles.css"> <!-- External CSS -->
</head>
<body>

  <!-- แถบนำทาง -->
  <nav>
    <a href="index.html">หน้าแรก</a>
    <a href="index.html" class="active">สินค้า</a>
    <a href="pages/about.html">เกี่ยวกับ</a>
    <a href="pages/contact.html">ติดต่อ</a>
    <a href="files/document.pdf" download>Download Document</a>
  </nav>

  <button class="back-btn" onclick="history.back()">Back</button>

  <!-- รายการสินค้า -->
  <div class="product-container">
    
    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product1.jpg" alt="Product 1">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 1</h2>
        <p class="product-price">฿1,999</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
        <button class="add-to-cart">เพิ่มลงตะกร้า</button>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product2.png" alt="Product 2">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 2</h2>
        <p class="product-price">฿1,599</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
        <button class="add-to-cart">เพิ่มลงตะกร้า</button>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product3.jpg" alt="Product 3">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 3</h2>
        <p class="product-price">฿999</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
        <button class="add-to-cart">เพิ่มลงตะกร้า</button>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product4.jpg" alt="Product 4">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 4</h2>
        <p class="product-price">฿1,299</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
        <button class="add-to-cart">เพิ่มลงตะกร้า</button>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product5.jpg" alt="Product 5">
      </div>
      <div class="product-info">
        <h2 class="product-title">Product 5</h2>
        <p class="product-price">฿899</p>
        <p class="product-description">รายละเอียดสินค้าตัวอย่าง</p>
        <button class="add-to-cart">เพิ่มลงตะกร้า</button>
      </div>
    </div>
  </div> 
</body>
</html>

```
```css
/* ตั้งค่าพื้นฐาน */
body {
    font-family: "Poppins", sans-serif;
    margin: 0;
    padding: 20px;
    background-color: #f8f9fa;
}

/* สไตล์เมนูนำทาง */
nav {
    display: flex;
    justify-content: center;
    background: #6c5ce7;
    padding: 15px;
    border-radius: 10px;
}

nav a {
    color: white;
    text-decoration: none;
    font-size: 18px;
    font-weight: 500;
    padding: 12px 20px;
    border-radius: 8px;
    transition: background 0.3s ease-in-out;
}

nav a:hover {
    background: #a29bfe;
}

nav a.active {
    background: white;
    color: #6c5ce7;
}

/* ปุ่มย้อนกลับ */
.back-btn {
    margin: 20px auto;
    display: block;
    padding: 10px 15px;
    font-size: 16px;
    background: #ff7675;
    color: white;
    border-radius: 5px;
    border: none;
    cursor: pointer;
    transition: 0.3s;
}

.back-btn:hover {
    background: #d63031;
}

/* สไตล์รายการสินค้า */
.product-container {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
    margin-top: 30px;
}

/* การ์ดสินค้า */
.product-card {
    width: 320px;
    border-radius: 12px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    background-color: white;
    text-align: center;
    padding: 20px;
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
}

/* รูปภาพสินค้า */
.product-image img {
    width: 100%;
    height: 220px;
    object-fit: cover;
    border-radius: 10px;
}

/* ข้อความสินค้า */
.product-title {
    color: #333;
    font-size: 24px;
    font-weight: bold;
    margin: 15px 0 8px;
}

.product-price {
    color: #00983a;
    font-size: 25px;
    font-weight: bold;
}

.product-description {
    color: #00bbff;
    font-size: 20px;
    line-height: 1.6;
    margin-bottom: 15px;
}

.product-button:hover {
    background: linear-gradient(to right, #574b90, #0652dd);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![Screenshot 2025-02-11 233258](https://github.com/user-attachments/assets/9abb4211-ad73-4dd0-8fb3-17e59430c95f)


### ตัวอย่างการใช้งาน: การสร้างเลย์เอาต์ Modern Dashboard

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .dashboard {
            display: grid;
            grid-template-areas: 
                "sidebar header"
                "sidebar main";
            grid-template-columns: 250px 1fr;
            grid-template-rows: auto 1fr;
            min-height: 100vh;
        }

        .header {
            grid-area: header;
            background: white;
            padding: 1rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .sidebar {
            grid-area: sidebar;
            background: #2c3e50;
            color: white;
            padding: 1rem;
        }

        .main-content {
            grid-area: main;
            padding: 1rem;
            background: #f5f7fa;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .chart-container {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 1rem;
        }

        .chart {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        @media (max-width: 768px) {
            .dashboard {
                grid-template-areas: 
                    "header"
                    "main";
                grid-template-columns: 1fr;
            }

            .sidebar {
                display: none;
            }

            .chart-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="dashboard">
        <header class="header">
            <h1>แดชบอร์ด</h1>
            <nav>
                <button>โปรไฟล์</button>
                <button>ออกจากระบบ</button>
            </nav>
        </header>

        <aside class="sidebar">
            <nav>
                <ul>
                    <li>หน้าแรก</li>
                    <li>รายงาน</li>
                    <li>การตั้งค่า</li>
                </ul>
            </nav>
        </aside>

        <main class="main-content">
            <div class="stats-grid">
                <div class="stat-card">
                    <h3>ยอดขายรวม</h3>
                    <p>฿150,000</p>
                </div>
                <div class="stat-card">
                    <h3>จำนวนออเดอร์</h3>
                    <p>1,234</p>
                </div>
                <div class="stat-card">
                    <h3>ลูกค้าใหม่</h3>
                    <p>45</p>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart">
                    <h3>กราฟแสดงยอดขาย</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
                <div class="chart">
                    <h3>สัดส่วนสินค้าขายดี</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งการแสดงผลต่าง ๆ ให้สวยงาม



### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Product Gallery</title>
  <link rel="stylesheet" href="styles.css"> <!-- External CSS -->
</head>
<body>

  <!-- แถบนำทาง -->
  <nav>
    <a href="index.html">หน้าแรก</a>
    <a href="index.html" class="active">สินค้า</a>
    <a href="pages/about.html">เกี่ยวกับ</a>
    <a href="pages/contact.html">ติดต่อ</a>
    <a href="files/document.pdf" download>Download Document</a>
  </nav>

  <button class="back-btn" onclick="history.back()">Back</button>

  <!-- หัวข้อสินค้า -->
  <h1 class="product-title">สินค้าทั้งหมด</h1>

  <!-- รายการสินค้า -->
  <div class="product-container">
    
    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product1.jpg" alt="Product 1">
      </div>
      <div class="product-info">
        <h2>Product 1</h2>
        <p class="product-price">฿1,999</p>
        <p class="product-description">น้ำหอมกลิ่นวนิลา</p>
        <button class="add-to-cart">🛒 เพิ่มลงตะกร้า</button>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product2.png" alt="Product 2">
      </div>
      <div class="product-info">
        <h2>Product 2</h2>
        <p class="product-price">฿1,599</p>
        <p class="product-description">น้ำหอมกลิ่นกุหลาบ</p>
        <button class="add-to-cart">🛒 เพิ่มลงตะกร้า</button>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product3.jpg" alt="Product 3">
      </div>
      <div class="product-info">
        <h2>Product 3</h2>
        <p class="product-price">฿999</p>
        <p class="product-description">น้ำหอมกลิ่นแฟนตาซี</p>
        <button class="add-to-cart">🛒 เพิ่มลงตะกร้า</button>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product4.jpg" alt="Product 4">
      </div>
      <div class="product-info">
        <h2>Product 4</h2>
        <p class="product-price">฿1,299</p>
        <p class="product-description">น้ำหอมกลิ่นมิดไนท์</p>
        <button class="add-to-cart">🛒 เพิ่มลงตะกร้า</button>
      </div>
    </div>

    <div class="product-card">
      <div class="product-image">
        <img src="images/products/product5.jpg" alt="Product 5">
      </div>
      <div class="product-info">
        <h2>Product 5</h2>
        <p class="product-price">฿899</p>
        <p class="product-description">น้ำหอมกลิ่นส้ม</p>
        <button class="add-to-cart">🛒 เพิ่มลงตะกร้า</button>
      </div>
    </div>
  </div> 
</body>
</html>

```
```css
/* ตั้งค่าพื้นฐาน */
body {
    font-family: "Poppins", sans-serif;
    margin: 0;
    padding: 0;
    background: linear-gradient(to bottom, #f0f4ff, #d6e4ff);
}

/* แถบนำทาง */
nav {
    display: flex;
    justify-content: center;
    gap: 20px;
    background: #4A90E2;
    padding: 12px 0;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

nav a {
    color: white;
    text-decoration: none;
    font-weight: bold;
    padding: 12px 20px;
    transition: 0.3s;
    border-radius: 8px;
}

nav a:hover {
    background: rgba(255, 255, 255, 0.2);
}

nav a.active {
    background: white;
    color: #4A90E2;
}

/* ปุ่มย้อนกลับ */
.back-btn {
    display: block;
    margin: 20px auto;
    padding: 10px 16px;
    background: #ff4d4d;
    color: white;
    font-size: 16px;
    border: none;
    cursor: pointer;
    border-radius: 8px;
    transition: 0.3s;
}

.back-btn:hover {
    background: #cc0000;
}

/* หัวข้อ */
.title {
    text-align: center;
    color: #333;
    font-size: 28px;
    margin: 20px 0;
}

/* Grid Layout สำหรับสินค้า */
.product-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
    padding: 20px;
    max-width: 1200px;
    margin: 0 auto;
}

/* การ์ดสินค้า */
.product-card {
    background: white;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    text-align: center;
    padding: 15px;
}

.product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

/* รูปภาพสินค้า */
.product-card img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-radius: 10px;
}

/* รายละเอียดสินค้า */
.product-title {
    font-size: 20px;
    color: #333;
    margin: 10px 0;
}

.product-price {
    font-size: 24px;
    color: #ff4d4d;
    font-weight: bold;
}

.product-description {
    font-size: 18px;
    color: #555;
    margin-bottom: 10px;
}

/* ปุ่มเพิ่มลงตะกร้า */
.add-to-cart {
    background: linear-gradient(to right, #4A90E2, #357ABD);
    color: white;
    font-size: 14px;
    border: none;
    padding: 10px 14px;
    border-radius: 15px;
    cursor: pointer;
    transition: 0.3s;
}

.add-to-cart:hover {
    background: linear-gradient(to right, #357ABD, #1C6BA0);
}

/* Responsive */
@media (max-width: 768px) {
    .product-container {
        grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    }
}

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![Screenshot 2025-02-12 001134](https://github.com/user-attachments/assets/e9907df1-4d13-4ee9-bd2c-b088b3eebd66)

