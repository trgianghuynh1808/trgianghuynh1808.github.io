---
top: 2
category: technology
tags:
  - react-native
  - expo
  - ubuntu
date: 2021-05-26
title: Hướng dẫn run project React Native trên Ubuntu với Expo, Android Studio
vssue-id: 10
---

Hi, Eri Huỳnh xin chào mọi người! Thời gian gần đây, mình có bắt đầu tìm hiểu thêm về React-native. Và khó khăn đầu tiên mình gặp phải
làm sao để có thể **Run Project React-native** trực tiếp trên máy **Ubuntu 20.04** để dev. Sau một thời gian tìm hiểu, thì mình đã lựa chọn giải pháp sử dụng **Expo** và một Emulator được tạo bởi **Android Studio** mình cảm thấy rất tiện dụng. Nên hôm nay mình sẽ chia sẻ với mọi người cách mà mình đang sử dụng để dev với project **React-native**.

![](https://images.viblo.asia/e1f7d060-d899-4d49-bd29-ce26d6ddc3c9.png)

Để có thể chạy `project React-native` mình cần làm theo các bước sau:

## 1. Cài đặt Node và npm

Nhiều bạn, sau khi cài xong node vẫn chưa thể run được project vì không tương thích với version Node hiện tại của project. Nên ở đây mình có thể mình sẽ cần cái thêm `nvm` để quản lý version cho Node

- **Cài nvm**

```
apt-get update
apt-get install build-essential libssl-dev

// install nvm
curl-o-https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash

// reload bash
source ~/.bashrc

// check version of nvm
nvm --version
```

- **Cài Node và npm**

```
// install latest node
nvm install node

// set default node version for nvm
nvm alias default node

// check version of node and npm
node -v
npm -v
```

## 2. Cài đặt Android Studio

- **Cài đặt Java**

```
sudo apt install openjdk-8-jre openjdk-8-jdk
```

- **Cài đặt Android Studio**

```
sudo snap install android-studio
```

Sau khi cài đặt `android-studio` hoàn tất. Bạn hãy mở ứng dụng `android-studio` lên, lúc này ứng dụng sẽ yêu cầu bạn cài đặt thêm các gói cần thiết để hoàn tất phần cài đặt. Bạn chỉ cần cài đặt theo hướng dụng của ứng dụng là được.

- **Cài đặt SDK cho Android Studio**

Sau khi bạn đã hoàn thành việc cài đặt `adnroid-studio`, bên dưới phần `Configure` lựa chọn `SDK Manager`.

<span style="display:block;text-align:center">![](https://images.viblo.asia/5c934a8b-5fe0-45dd-9240-5816efc4736d.png)</span>

Tiếp theo bạn hãy lựa chọn SDK phù hợp để chạy project của bạn. Nếu là lần đầu cài đặt bạn có thể chọn theo mình.

![](https://images.viblo.asia/11b2b216-a78e-4566-8654-6e1b5bc704ba.png)

- **Tạo máy ảo trên Android Studio**

Cũng tương tự như với cài đặt `SDK`, bạn hãy vào `Configure` lựa chọn `AVD Manager`.

<span style="display:block;text-align:center">![](https://images.viblo.asia/131123ed-2752-40e7-826e-7fd194d5f02e.png)</span>

Giao diện `AVD Manager` sẽ hiện ra, sau đó hãy chọn `Create Virtual Device...` đối với trường hợp lần đầu, chưa có máy ảo đã tạo trước đó.

<span style="display:block;text-align:center">![](https://images.viblo.asia/276c1e82-8f7e-4578-b5c0-b972b76d35f1.png)</span>

Lựa chọn thiết bị cũng như kích cỡ màn hình mà bạn muốn tạo máy ảo. Sau đó chọn `Next`.

![](https://images.viblo.asia/f1297825-9149-4f52-92d0-bc136306e08d.png)

Lựa chọn `system image` cho thiết bị. Nếu lựa chọn của bạn chưa được Down, hãy chọn `Download` tương ứng với từng dòng trong bảng `system image`

![](https://images.viblo.asia/afaa81e7-848c-450d-8e7c-d1e7c9c65388.png)

Cuối cùng là đặt tên cho thiết bị, và chọn `Finish` để hoàn tất việc tạo máy ảo.

![](https://images.viblo.asia/2c76d7d4-7884-4e62-9f57-31a789d46c69.png)

Sau khi tạo máy ảo hoàn tất ở giao diện `ADV Manager` bạn sẽ thấy danh sách các máy ảo mà bạn đã tạo. Bây giờ bạn có thể Ấn nút `Play` để run máy ảo vừa tạo rồi :D.

<span style="display:block;text-align:center">![](https://images.viblo.asia/dcd2d811-af82-4373-9a01-bb61de3bee2c.png)</span>

## 3. Tạo và run project với Expo

- Mình sẽ init project react-native với `Expo CLI`. Nếu chưa có bạn hãy cài đặt `Expo CLI` theo câu lệnh bên dưới.

```
npm install --global expo-cli
```

- Init & start project

```
// init react-native project with name "my-app"
expo init my-app

cd my-app

// start project
expo start
```

- Sau khi start project, bạn sẽ thấy một browser để quản lý của `expo`. Lựa chọn `Run on Android device/emulator` để connect với máy ảo mà bạn vừa tạo.

![](https://images.viblo.asia/dd0927cf-762c-4b67-aebc-14bfc2f89230.png)

## Tạm kết

Yup :fireworks::fireworks: hãy tận hưởng thành quả nào :D Vậy là mình đã hoàn thành các bước để run project `react-native`. Nếu gặp khó khăn gì trong quá trình cài đặt hãy comment ở phần bình luận nhé. Mình và mọi người sẽ hỗ trợ các bạn, chúc các bạn thành công.

Hãy ủng hộ, follow và cho mình những nhận xét để mình dần cải thiện nhé. Eri Huỳnh Cám ơn mọi người :heartpulse::heartpulse::heartpulse:
