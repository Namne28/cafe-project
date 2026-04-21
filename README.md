# ☕ Hạt Vàng Café — Website Bán Cà Phê

## Cấu trúc dự án

```
cafe-project/
├── public/
│   └── index.html        # Website chính
├── data/
│   └── menu.json         # Data thực đơn (24 món, 5 danh mục)
├── Dockerfile            # Build image Docker
├── docker-compose.yml    # Chạy với Docker Compose
├── nginx.conf            # Cấu hình Nginx
└── README.md
```

## Chạy bằng Docker

### Cách 1: Docker Compose (khuyên dùng)

```bash
# Build và chạy
docker-compose up -d

# Xem logs
docker-compose logs -f

# Dừng
docker-compose down
```

### Cách 2: Docker thuần

```bash
# Build image
docker build -t hat-vang-cafe .

# Chạy container
docker run -d -p 3000:80 --name cafe hat-vang-cafe
```

Sau đó mở trình duyệt: **http://localhost:3000**

## Chạy bằng VS Code

1. Cài extension **Docker** cho VS Code
2. Click chuột phải vào `docker-compose.yml` → **Compose Up**
3. Hoặc dùng terminal tích hợp chạy lệnh trên

## Thực đơn (menu.json)

| Danh mục | Số món |
|----------|--------|
| Cà Phê Việt | 5 |
| Espresso | 6 |
| Trà & Trà Sữa | 5 |
| Sinh Tố & Nước Ép | 4 |
| Đặc Biệt | 4 |

## Tính năng website

- Lọc theo danh mục và nhiệt độ (nóng/lạnh)
- Giỏ hàng sidebar
- Tăng/giảm số lượng từng món
- Đặt hàng với thông báo toast
- Responsive mobile

## Thêm món vào menu

Mở file `data/menu.json` và thêm item vào mảng `items` của danh mục tương ứng:

```json
{
  "id": 25,
  "name": "Tên món",
  "price": 50000,
  "desc": "Mô tả ngắn",
  "hot": true,
  "cold": false,
  "popular": false
}
```
