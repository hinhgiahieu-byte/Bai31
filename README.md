<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <title>Kiểm tra HTML - Javascript 05</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 30px;
        }
        form {
            background-color: #f2f2f2;
            padding: 20px;
            border-radius: 5px;
            width: 300px;
        }
        div {
            margin-bottom: 10px;
        }
        label {
            display: inline-block;
            width: 70px;
        }
        input {
            padding: 5px;
            width: 180px;
        }
        button {
            padding: 8px 15px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
        #ketQua {
            margin-top: 15px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h2>Tính tổng các số chia hết cho 3 trong khoảng</h2>

    <form onsubmit="handleSubmit(event)">
        <div>
            <label for="soDau">Số đầu:</label>
            <input type="number" id="soDau" required>
        </div>
        <div>
            <label for="soCuoi">Số cuối:</label>
            <input type="number" id="soCuoi" required>
        </div>
        <button type="submit">Submit</button>
    </form>

    <p id="ketQua"></p>

    <script>
        function handleSubmit(event) {
            // Ngăn chặn trang web reload lại khi bấm Submit
            event.preventDefault();

            // Lấy giá trị nhập từ 2 ô input và chuyển sang kiểu số nguyên
            const soDau = parseInt(document.getElementById("soDau").value);
            const soCuoi = parseInt(document.getElementById("soCuoi").value);

            let tong = 0;

            // Đảm bảo lấy đúng khoảng từ số nhỏ đến số lớn
            const min = Math.min(soDau, soCuoi);
            const max = Math.max(soDau, soCuoi);

            // Vòng lặp duyệt qua các số trong khoảng từ min đến max
            for (let i = min; i <= max; i++) {
                // Kiểm tra điều kiện chia hết cho 3 (số dư % 3 bằng 0)
                if (i % 3 === 0) {
                    tong += i;
                }
            }

            // In kết quả ra màn hình Console (F12)
            console.log("Tổng các số chia hết cho 3 là: " + tong);

            // In kết quả ra giao diện web
            document.getElementById("ketQua").innerText = 
                "Tổng các số chia hết cho 3 từ " + min + " đến " + max + " là: " + tong;
        }
    </script>

</body>
</html>
