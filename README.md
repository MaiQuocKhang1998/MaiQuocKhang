<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lễ Hội Khmer</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1em 0;
        }
        nav {
            background-color: #444;
            color: white;
            text-align: center;
            padding: 0.5em 0;
        }
        nav a {
            color: white;
            text-decoration: none;
            padding: 0 1em;
        }
        main {
            padding: 20px;
        }
        #danhSachLeHoi {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
        }
        .leHoi {
            width: 300px;
            margin: 20px;
            border: 1px solid #ddd;
            padding: 15px;
            background-color: white;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .leHoi img {
            max-width: 100%;
            height: auto;
            margin-bottom: 10px;
        }
        .leHoi button {
            background-color: #5cb85c;
            color: white;
            padding: 10px 15px;
            border: none;
            cursor: pointer;
        }
        #chiTietLeHoi {
            background-color: white;
            padding: 20px;
            margin-top: 20px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            display: none; /* Ẩn ban đầu */
        }
        #lienHe {
            background-color: white;
            padding: 20px;
            margin-top: 20px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1em 0;
            position:relative;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Lễ Hội Của Người Dân Tộc Khmer</h1>
    </header>
    <nav>
        <a href="#danhSachLeHoi">Danh sách lễ hội</a>
        <a href="#lienHe">Liên hệ</a>
    </nav>
    <main>
        <section id="danhSachLeHoi">
            <div class="leHoi">
                <img src="cholchnamthmay.jpg" alt="Tết Chôl Chnăm Thmây">
                <h3>Tết Chôl Chnăm Thmây</h3>
                <p>Thời gian: 13-16/04</p>
                <button class="xemChiTiet" data-index="0">Xem chi tiết</button>
            </div>
            <div class="leHoi">
                <img src="sendonta.jpg" alt="Lễ hội Sene Đôn Ta">
                <h3>Lễ hội Sene Đôn Ta</h3>
                <p>Thời gian: 29/8-01/9</p>
                <button class="xemChiTiet" data-index="1">Xem chi tiết</button>
            </div>
            <div class="leHoi">
                <img src="okombok.jpg" alt="Lễ hội Ok Om Bok">
                <h3>Lễ hội Ok Om Bok</h3>
                <p>Thời gian: 14-15/10</p>
                <button class="xemChiTiet" data-index="2">Xem chi tiết</button>
            </div>
        </section>
        <section id="chiTietLeHoi">
            <h2>Chi tiết lễ hội</h2>
            <div id="noiDungChiTiet">
                </div>
        </section>
        <section id="lienHe">
            <h2>Liên hệ</h2>
            <form>
                <label for="ten">Tên:</label>
                <input type="text" id="ten" name="ten"><br><br>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email"><br><br>
                <label for="tinNhan">Tin nhắn:</label><br>
                <textarea id="tinNhan" name="tinNhan" rows="4" cols="50"></textarea><br><br>
                <input type="submit" value="Gửi">
            </form>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 Lễ Hội Khmer</p>
    </footer>
    <script>
        const cacLeHoi = [
            {
                ten: "Tết Chôl Chnăm Thmây",
                thoiGian: "13-16/04",
                diaDiem: "Các tỉnh miền Tây Nam Bộ",
                moTa: "Tết cổ truyền mừng năm mới của người Khmer...",
                hinhAnh: "cholchnamthmay.jpg",
            },
            {
                ten: "Lễ hội Sene Đôn Ta",
                thoiGian: "29/8-01/9",
                diaDiem: "Các chùa Khmer",
                moTa: "Lễ hội cúng ông bà tổ tiên...",
                hinhAnh: "sendonta.jpg",
            },
                        {
                ten: "Lễ hội Ok Om Bok",
                thoiGian: "14-15/10",
                diaDiem: "Sóc Trăng",
                moTa: "Lễ hội cúng trăng của người Khmer...",
                hinhAnh: "okombok.jpg",
            },
        ];
        const chiTietLeHoi = document.getElementById("chiTietLeHoi");
        const noiDungChiTiet = document.getElementById("noiDungChiTiet");
        const xemChiTietButtons = document.querySelectorAll(".xemChiTiet");
        xemChiTietButtons.forEach(button => {
            button.addEventListener("click", function() {
                const index = this.getAttribute("data-index");
                noiDungChiTiet.innerHTML = `
                    <h2>${cacLeHoi[index].ten}</h2>
                    <img src="${cacLeHoi[index].hinhAnh}" alt="${cacLeHoi[index].ten}" style="max-width: 100%;">
                    <p>Thời gian: ${cacLeHoi[index].thoiGian}</p>
                    <p>Địa điểm: ${cacLeHoi[index].diaDiem}</p>
                    <p>${cacLeHoi[index].moTa}</p>
                `;
                chiTietLeHoi.style.display = "block";
            });
        });
    </script>
</body>
</html>
