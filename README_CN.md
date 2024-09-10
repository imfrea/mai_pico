# Mai Pico - Maimai 风格的迷你控制器
### 本分支的目的在于提供更详细的制作文档，物料清单，以及外壳设计（中文语言）。
[Click here for the English version of this guide.](README.md)

<img src="doc/main.jpg" width="80%">  
<img src="doc/assembled.jpg" width="80%">

为了省事，本文档是我从原先英文版翻译回中文的，高度依赖了 GitHub Copilot (GPT)，所以语气可能怪怪的，见谅。

**特性:**
* 使用 15.6 英寸的便携式屏幕制作。
* 类似街机的体验。
* 可以双人游戏。
* 内置支持 AIME。
* 所有源文件开放。

感谢许多尊敬的爱好者和公司将他们的工具或材料免费或开源（KiCad，OnShape，InkScape，Raspberry 相关工具, 嘉立创）。

## 注意事项
这个项目是我众多项目里最复杂的一个。
* 它需要定制蚀刻的 ITO 玻璃和便携式显示器。
* 严重依赖 3D 打印。
* 需要焊接微小组件的技能。
* 需要许多其他 DIY 动手技能。
* IO PCB 仍处于原型状态，它可以工作，但布局和连接器并不完美。您可能需要直接从 Pi Pico 的引脚焊接。我太懒了，原型之后就没有做新版本。
* 我没有设计外壳，需要你自己来设计，让它看起来漂亮且结构稳定，发挥你的想象力，跟随你的品味。

## 查看我的其他项目
你也可以查看我其他的酷炫项目。

<img src="https://github.com/whowechina/popn_pico/raw/main/doc/main.jpg" height="100px">
<img src="https://github.com/whowechina/iidx_pico/raw/main/doc/main.jpg" height="100px">
<img src="https://github.com/whowechina/iidx_teeny/raw/main/doc/main.jpg" height="100px">
<img src="https://github.com/whowechina/chu_pico/raw/main/doc/main.jpg" height="100px">
<img src="https://github.com/whowechina/mai_pico/raw/main/doc/main.jpg" height="100px">
<img src="https://github.com/whowechina/diva_pico/raw/main/doc/main.jpg" height="100px">
<img src="https://github.com/whowechina/aic_pico/raw/main/doc/main.gif" height="100px">
<img src="https://github.com/whowechina/groove_pico/raw/main/doc/main.gif" height="100px">

* Popn Pico: https://github.com/whowechina/popn_pico
* IIDX Pico: https://github.com/whowechina/iidx_pico
* IIDX Teeny: https://github.com/whowechina/iidx_teeny
* Chu Pico: https://github.com/whowechina/chu_pico
* Mai Pico: https://github.com/whowechina/mai_pico
* Diva Pico: https://github.com/whowechina/diva_pico
* AIC Pico: https://github.com/whowechina/aic_pico
* Groove Pico: https://github.com/whowechina/groove_pico

## **声明** ##
我在个人时间内制作了这个项目，没有任何经济利益或赞助。我将继续改进这个项目。我已尽我所能确保所有内容的准确性和功能性，但总有可能出现错误。如果你因使用这个开源项目而造成时间或金钱的损失，我不能负责。感谢你的理解。

查看我 GitHub 主页，上面有很多其他项目。

https://github.com/whowechina/

## 关于许可证
它是 CC-NC 授权。所以你只能给自己和你的朋友 DIY，不能利用这个项目赚钱。


## 制作集锦
开始之前，我想给你看一些爱好者的作品，来鼓励你继续下去。

### **Lavide 的作品**
  Lavide 制作了一个漂亮的紧凑型一体化 Mai Pico 机框！  
  <img src="doc/lavide_1.jpg" width="30%"><img src="doc/lavide_2.jpg" width="30%"><img src="doc/lavide_3.jpg" width="21.65%">

### **Romper 的作品**
  Romper 利用 Mai Pico 的触摸设计制作了一个全尺寸的控制器。  
  <img src="doc/romper_1.png" width="28%"><img src="doc/romper_2.jpg" width="50%">

### **imfrea 的作品**
  imfrea 给 Mai Pico 设计了一套平价又好看的亚克力外壳。  
  <img src="doc/imfrea_1.jpg" width="30%"><img src="doc/imfrea_2.jpg" width="30%">  
  你可以从他的 fork 分支下载亚克力外壳设计。  
  https://github.com/imfrea/mai_pico

## 如何制作
[BOM详单与采购建议](BOM_list_CN.md)

### PCB
* 去 JLCPCB 并使用 gerber zip 文件（最新的 `Production\PCB\mai_io_v*.zip` 和 `Production\PCB\mai_button_v*.zip`）下单，常规 FR-4 板，厚度 1.6mm。你需要 1x io PCB 和 8x 按钮 PCBs 来构建一个 Mai Pico con。  
  <img src="doc/pcbs.jpg" width="50%">
* 1x Raspberry Pico Pi Pico 或 Pico W。  
  https://www.raspberrypi.com/products/raspberry-pi-pico
  
  注意另一侧的 3 个引脚，它们很难焊接，可能会留下气泡（只需焊接TP2 TP3 给模块上的这两个焊盘预先上锡可提高焊接成功率）。  
  <img src="doc/solder_usb_txrx.jpg" width="60%">
* 1x USB Type-C 插座（918-418K2023S40001 或 KH-TYPE-C-16P）
* 2x 0603 5.1kohm 电阻（R20，R21）用于 USB，如果你打算直接使用 Pi Pico 上面原生的 USB 插座，那么 Type-C 插座和电阻都可以省去，焊接也会简单不少。

* 3x MPR121 模块，市场上有许多类型，选择像这样的。
  https://www.sparkfun.com/products/retired/9695 

  在将 MP121 模块焊接到主 PCB 板之前，记得用小刀**切断 ADDR 和 GND 之间的微小连线**，注意绝对不要切过头（只需要处理U3 U4这两个模块）。  
  操作方法可以观看视频 https://www.bilibili.com/video/BV1gt42157SU/  
  <img src="doc/mpr121_cut.png" width="40%">
* 因为我们使用的是 MPR121 模块，而不是芯片，所以 U5、U6、U7 区域的离散组件留空。  
  焊接完成后，可以用手扫过金手指来测试功能，每个MPR121对应的电极范围如下：
  <img src="doc/mpr121_electrode.png" width="60%">
* 1x SN74LV1T34DBVR（SOT-23-5）电平转换器（U8），如果你找不到，可以用 0603 10ohm 电阻（R4）替代。
  https://www.lcsc.com/product-detail/Buffer-Driver-Transceiver_Texas-Instruments-SN74LV1T34DBVR_C100024.html
* 4x 0603 1uF（0.1~1uF 都可以）电容器（C1，C2，C3，C7），可选，推荐。
* 16x WS2812B-3528 RGB LED（每个按钮需要两个）。
* 8x Kailh Choc v1 键盘开关，线性的，30gf 到 45gf 的。
  https://www.kailhswitch.com/mechanical-keyboard-switches/low-profile-key-switches/burnt-orange-switch.html
* 1x PN532 NFC 模块和一些细电线, 只有需要 AIME 的时候才用得上.  
  https://www.elechouse.com/product/pn532-nfc-rfid-module-v4/  
  你需要把它焊接到 MPR121 所在的 I2C 总线上（GPIO 6 and 7）。

### ITO 玻璃
* 找一个服务定制蚀刻 ITO 镀膜玻璃。AutoCAD 文件是 `Production\CAD\mai_pico_ito_v*.dwg`。使用 2mm 厚，10-20ohm 平方电阻的 ITO 镀膜玻璃。  
  <img src="doc/ito_glass.jpg" width="70%">
* ITO 镀膜玻璃通过 "斑马线"（1.6mm 间距：0.8mm 黑色部分和 0.8mm 透明部分）连接到 IO PCB。使用 200°C 的硅加热头将斑马线粘贴到 PCB 的金手指部分和 ITO 镀膜玻璃上。这种线的正式名称是 "热压密封连接器"。  
  * 如果你无法辨别哪一面是ITO涂层，可以使用万用表的蜂鸣裆来测试（请避免直接用表笔或其他尖锐物品接触涂层，例如使用两片铜箔）。
  * 在压接之前请将PCB金手指擦拭干净。务必完全对齐金手指和黑色部分，压实每一处，做到平整不留下气泡。（排线的总长度建议在5cm以内）。可观看视频教程：https://www.bilibili.com/video/BV1Qp42127bc/
  <img src="doc/zebra_cable.jpg" width="70%">
* 定制 ITO 镀膜玻璃相对较贵，但我们的尺寸小，所以并不像街机那么贵。这是我订购 ITO 玻璃的店铺，我订购的时候的最小批量是 5 件。据我所知，他们只在中国提供服务。我和他们店铺没有关联，此处提供链接并不表示我为他们的产品和服务负责。  
  https://shop378788148.taobao.com/?spm=2013.1.1000126.2.305e16c4LFf1GW

### 按键环
* 从 `Production\3DPrint\mai_*.stl` 打印出 8 套 `底座`、`连接板`、`按钮` 和 `盖子`。
* 购买 8 根 2mm（直径）* 40mm（长度）的钢轴，它们用作按钮铰链。
* 这是如何组装它们的方法，这个渲染图像中没有显示铰链轴和 PCB 上的组件。  
  <img src="doc/assemble.jpg" width="80%">
* 这是我如何组装环的方法。请注意，这些图片中缺少按钮开关的线路。
  * 所有离散组件已准备好。  
    <img src="doc/assemble_1.jpg" width="60%">
  * 首先焊接按钮 PCB。  
    <img src="doc/assemble_2.jpg" width="60%">
  * WS2812B是区分极性的，灯珠的左上角缺角要对准PCB丝印上的缺角。建议在测试LED均可点亮后再焊接上轴体。
  
  * 按键 PCB 使用细小且柔软的 3 线电缆串联，它们是 G、IN/OUT、V，分别代表地、信号进/出和电源（每一段线的长度约为4cm）。按钮开关信号引脚还没有焊接，你可以后面再焊接。请不用担心按钮 GPIO 的顺序，因为它们可以通过命令行重新映射。    
  你需要将每个按键板的BT ?分别连接到io 板上对应位置（可以焊接到BT1~8中间的孔中，或Raspberry Pico模块的GPxx上），连线则可以埋藏于按键PCB下的空隙中，然后汇聚再从link之间的孔洞中引出。
  可参照：https://github.com/whowechina/mai_pico/issues/8#issue-2152602904  
    <img src="doc/button_v111_top.png" width="60%">
    <img src="doc/io_top.png" width="60%">   
  * 按照此顺序连接则无需后续调整（“①”数字标号是按钮的游戏顺序，BTx/GPx是io板上的位置）。  
  [接线拓扑图](doc/wiring_route.pdf)   
    <img src="doc/assemble_5_order.jpg" width="60%">
    <img src="doc/assemble_3.jpg" width="60%">
  * 如果你还需要Service（服务键），Test（测试键），Navigate（选择键），Coin（投币键）可自行补丁。    
  可参照https://github.com/whowechina/mai_pico/issues/7#issuecomment-1938689911
  * 你需要 3M5423 UHMW 胶带（或类似的硬且超滑的 PTFE 胶带，厚度 0.2-0.3）。它用来润滑触摸键开关的按钮表面。  
    <img src="doc/button_lub.jpg" width="60%">
  * 将 3D 打印的部件和 PCBs 组装在一起。  
    <img src="doc/assemble_4.jpg" width="60%">
  * 使用轴稍微扩大支撑孔（如有条件可使用2.1mm麻花钻头），然后涂上一些键盘开关润滑剂，如 Krytox 205G0，使轴超级光滑。  
    <img src="doc/assemble_5.jpg" width="60%">
  * 每个 `连接板` 需要 8x M2*4mm 螺丝将两个 `底座` 连接在一起。  
    <img src="doc/assemble_6.jpg" width="60%">
  * 安装 `盖子`，每个需要 2x M2*5mm 螺丝。  
    <img src="doc/assemble_7.jpg" width="60%">

### 便携显示器
  * 分辨率：1920*1080，尺寸：15.6 英寸，刷新率：120Hz（推荐）或 60Hz，内置扬声器。
  * 它们很容易找到。选择闲鱼上有小瑕疵的会便宜得多，也一样很好用。
  * 有两种类型的驱动板，一种只有 micro-HDMI，另一种支持 type-C 显示（方便连接 Nintendo Switch）。两种都可以。  
  https://www.amazon.com/s?k=portable+display+15.6+120hz&s=price-asc-rank&crid=1CCA2EAYLZDBE&qid=1697276847&sprefix=portable+display+15.6+120hz%2Caps%2C387&ref=sr_st_price-asc-rank&ds=v1%3AqoS0mks05q225yuL8reh50fEEBkTZ583nMPEZJwjXAk

### 粘合到一起
  * 我使用 3M VHB 胶带（0.5mm 或 1mm 厚）将按钮环、ITO 玻璃和显示器粘在一起。
  * 只使用一点胶带，我使用 4 小块胶带将 ITO 玻璃粘到显示器上，另外 4 小块胶带将按钮环粘到 ITO 玻璃上。
  * 不要在 ITO 玻璃的走线上贴胶带，你可以在某个角度光线下看到 ITO 的走线。

### 外壳
  * 本分支提供了一个简易实用的外壳，由两大块亚克力板和铝型材组成。兼容现有的电路设计，制造成本低廉（约70RMB 完整版约120RMB），支持100和75mm的VESA显示器安装孔。详见`Production\Case`和[BOM详单](BOM_list_CN.md)  
  效果如下图（仅供参考，有些许不一样）  
    <img src="doc/casing_front.jpg" width="60%">
	<img src="doc/casing_back.jpg" width="60%">  
  * 装配结构如下
    <img src="doc/assemble_case_first_layer.jpg" width="100%">
    <img src="doc/assemble_case_second_layer.jpg" width="100%">
    <img src="doc/assemble_case_third_layer.jpg" width="100%">
    <img src="doc/assemble_case_fourth_layer.jpg" width="100%">

### 固件
* UF2 文件在 `Production\Firmware` 文件夹中。
* 对于新的构建，连接 USB 到 PC 时按住 BOOTSEL 按钮，会出现一个名为 "RPI-RP2" 的磁盘。将 UF2 固件二进制文件拖入其中。就这样。
* LED 和 Touch 协议的实现遵循 Sucareto 在 https://github.com/Sucareto/Mai2Touch 上的研究。
* 它有一个命令行进行配置。你可以使用这个 Web Serial Terminal 连接到 Mai Pico 的 USB 串口。（注意："?" 是帮助）  
  https://googlechromelabs.github.io/serial-terminal/  
  建议使用Chrome内核的浏览器打开，或者使用Putty或其他类似的串口连接工具 https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
  <img src="doc/cmd.png" width="60%">
  * 当你点击这个网页的 Connect 按钮后，你能看到每个端口的名称。  
   <img src="doc/ports.png" width="60%">
* 可以使用 `gpio` 命令重新映射按钮 GPIOs，固件支持 8 个主按钮和 4 个辅助按钮（分别是：Test, Service, Navigate, Coin）。
* 可以使用 `touch` 命令重新映射触摸键。对于用 ITO 膜手作触摸板，或者自己定制了引脚不同的 ITO 镀膜玻璃的朋友，这个命令会很有用:
  * `touch` 不带参数，可以用来检测当前按下的触摸键。
  * `touch 1 9 E6` 是映射第二个 MPR121 传感器的电极 9 到 “E6”，注意 “XX” 表示不连接任何触摸键。
* 可以使用 `rgb` 命令为每个按钮分配串联的 RGB LED 数量。
* 可以通过 `level` 命令调整 LED 的亮度。
* 有 MPR121 参数调整和灵敏度设置，自己探索。
* 它实现了 3 个 COM 端口，一个用于命令行，另外两个用于 LED 和 Touch。通过向命令行发出 `whoami`，每个 COM 端口都会打印它们的身份。  
  * 如果你的串口号混乱，则可以通过此方式调整（修改端口号后需要重新拔插USB）：https://learn.microsoft.com/en-us/answers/questions/452998/how-to-assign-static-com-port-number-to-a-device  
  * 如果你的串口被占用，通过此方式解除（如有“蓝牙链接上的标准串行”占用了指定端口号请将其卸载）：https://soldered.com/learn/how-to-clear-or-reset-com-ports/
* 按钮信号通过 HID Joystick 或 HID NKRO（键盘）发送到主机。有两套 NKRO 键映射，使用 `hid <joy|key1|key2>` 在它们之间切换。在 NKRO 模式下，键映射是：
  * key1：`WEDCXZAQ`-按键环，`3`-Select
  * key2（小键盘）：`89632147`-按键环，`*`-Select
  * 上述两套都有：`F1`-Test `F2`-Service `F3`-投币
* `factory` 用来复位到默认配置。当固件升级时，老配置可能失效，这时候请复位到默认配置，然后重新插拔一下控制器。

### 故障排除
* 连接电脑无反应，提示无法识别的USB设备，未知 USB 设备所需电量超出该端口所能提供的电量
  * 请检查焊接，Type-C插座是否虚焊，+5V +3V3网络是否存在连锡短路的情况。并考虑更换另一条USB数据线。
* 触摸区域无反应，自动触发，无规律跳动
  * 请检查MPR121模块（芯片）是否焊接正确良好，模块背面ADD与GND之间连线是否切断。斑马线是否压接良好。
  * 在USB串口中使用 `raw` 命令查看各个Sensor是否均为OK，电极数值（800~900左右为正常）。
  * 请将ITO玻璃图案区域悬空，不要紧挨物体表面。ITO玻璃要固定在原位，不可自由活动，特别是在设备上电后。
* 灯光不亮，灯光自某个按键后不亮
  * 请检查灯珠缺口方向是否正确，LED信号线连接，断点处按键PCB电容旁的WS2812是否虚焊或损坏。
* 灯光颜色无法随游戏同步
  * 检查LED端口是否正确设置，请在游戏启动之前连接设备。
* 单个或连续多个按键失效
  * 请检查对应按键PCB上的BT ?和BUTTON_GND线缆的连通性。

## CAD 源文件
我正在使用 OnShape 的免费订阅。它很强大，但不能将原始设计存档到本地，所以我只能在这里分享链接。STL/DXF/DWG 文件是从这个在线文档导出的。  
https://cad.onshape.com/documents/d8b39d27c9cb7990d9ce4d46/w/2c1baa71e391bfd1246f122b/e/f87f0f1c373fe2186ddc5c9c?renderMode=0&uiState=652a665608b4e07137e3861a
