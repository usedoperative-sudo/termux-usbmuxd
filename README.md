# Termux-Usbmuxd (Improved)

Chạy `usbmuxd` không cần root trên Termux thông qua `termux-usb`. Phiên bản cải tiến này hỗ trợ tự động phát hiện thiết bị và tối ưu hóa quy trình kết nối.

## Cải tiến mới

- **Tự động phát hiện thiết bị**: Không còn cần chạy `termux-usb -l` để tìm đường dẫn thủ công. Chỉ cần gõ `termux-usbmuxd`.

- **Tích hợp môi trường**: Tự động cấu hình `USBMUXD_SOCKET_ADDRESS` trong `.bashrc`.

- **Ổn định hơn**: Xử lý quyền truy cập USB mượt mà hơn với flag `-r`.

- **Tương thích cao**: Hoạt động tốt với `libimobiledevice` và `ideviceinstaller` trên các dòng iPhone mới nhất.

## Cài đặt

Mở Termux và chạy lệnh sau:

```bash
pkg install -y git
git clone https://github.com/vuphan0246810/termux-usbmuxd
cd termux-usbmuxd
bash install.sh
```

## Cách sử dụng

1. **Kết nối iPhone** vào điện thoại Android qua cáp USB-OTG.

1. **Chạy lệnh**:

   ```bash
   termux-usbmuxd
   ```

1. **Cấp quyền**: Một hộp thoại Android sẽ hiện lên yêu cầu quyền truy cập USB, hãy chọn "OK".

1. **Ghép nối**:

   ```bash
   idevicepair pair
   ```

   (Nhấn "Tin cậy/Trust" trên màn hình iPhone nếu được hỏi ).

1. **Kiểm tra kết nối**:

   ```bash
   idevicename
   ```

## Các lệnh hữu ích khác

- `ideviceinfo`: Xem thông tin chi tiết thiết bị.

- `ideviceinstaller -l`: Liệt kê các ứng dụng đã cài đặt.

- `ideviceinstaller -i app.ipa`: Cài đặt file IPA.

## Khắc phục lỗi

Nếu không tìm thấy thiết bị:

1. Đảm bảo cáp OTG hoạt động tốt.

1. Thử rút cáp và cắm lại.

1. Chạy `termux-usb -l` để kiểm tra xem Android có nhận diện được thiết bị không.
