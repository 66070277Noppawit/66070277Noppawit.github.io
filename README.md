# Physical Computing Project 2024 - IT KMITL
---
## จัดทำโดย

![Noppawit](Image/Noppawit.jpg)
**66070277 นพวิชญ์ ประทุมชาติ**
  
**66070245 คณิตพัฒน์ เตชะอัครเศรษฐ์**

![Thanaphat](Image/Thanaphat.jpg)
**66070266 ธนภัทร อิ่มใจ**

โปรเจกต์ **"EmotiFace LED"** นี้มีวัตถุประสงค์เพื่อสร้างระบบแสดงสีหน้าทางดิจิทัลที่สามารถใช้ในงานคอสเพลย์ได้ โดยใช้แผง LED ขนาด 32x8 ที่สามารถปรับเปลี่ยนเป็นสีหน้าต่าง ๆ ผ่านการควบคุมทางไกลหรือเซ็นเซอร์ในอนาคต เป้าหมายหลักคือเพื่อให้คอสเพลเยอร์สามารถแสดงอารมณ์ผ่านหน้ากากหรือหน้าจอ LED ที่แสดงสีหน้าแบบต่าง ๆ ได้ เพิ่มความสนุกสนานและเพิ่มระดับความสมจริงของตัวละคร

---

## บทคัดย่อ (Abstract)

โครงการนี้มีวัตถุประสงค์ในการพัฒนา **"EmotiFace LED"** ซึ่งเป็นอุปกรณ์ที่สามารถแสดงสีหน้าและอารมณ์ผ่านแผงไฟ LED ชนิด WS2812B ขนาด 32x8 เพื่อนำไปใช้ในกิจกรรม Cosplay โดยตัวอุปกรณ์นี้จะสามารถแสดงสีหน้าในลักษณะต่างๆ เช่น การยิ้ม ความเศร้า และการแสดงออกทางอารมณ์อื่นๆ ได้อย่างสมจริง และมีความยืดหยุ่นในการใช้งานผ่านการควบคุมจากระยะไกลด้วยระบบ IoT (Internet of Things)

อุปกรณ์ “EmotiFace LED” นี้ถูกออกแบบมาเพื่อให้สามารถปรับเปลี่ยนสีหน้าได้ตามต้องการผ่านคำสั่งจากผู้ใช้ ทำให้การแสดงสีหน้าสามารถปรับให้สอดคล้องกับสถานการณ์ต่างๆ ได้ โดยใช้ระบบไฟ LED ซึ่งทำให้เกิดความชัดเจนและสามารถดึงดูดความสนใจได้ดี นอกจากนี้ อุปกรณ์นี้ยังมีขนาดกะทัดรัดและง่ายต่อการติดตั้ง โดยเฉพาะสำหรับนักแสดง Cosplay ที่ต้องการการแสดงออกทางสีหน้าที่โดดเด่นและน่าดึงดูด

ระบบนี้ยังสามารถเชื่อมต่อกับแพลตฟอร์มต่างๆ ผ่านระบบ MQTT Protocol ทำให้สามารถควบคุมอุปกรณ์ได้จากระยะไกล ซึ่งช่วยเพิ่มความสะดวกในการใช้งาน และเปิดโอกาสให้นำไปใช้ในกิจกรรมต่างๆ ที่ต้องการการสื่อสารด้วยภาพและแสงสี นอกจากนี้ ยังสามารถพัฒนาและปรับแต่งเพิ่มเติมเพื่อใช้งานในด้านอื่นๆ เช่น การแสดงสีหน้าในสื่อบันเทิง งานนิทรรศการ หรืองานสื่อสารเชิงโต้ตอบ

**ผู้ประดิษฐ์**  
66070277 นายนพวิชญ์ ประทุมชาติ  
66070245 นายคณิตพัฒน์ เตชะอัครเศรษฐ์  
66070266 นายธนภัทร อิ่มใจ  
**คณะ**: เทคโนโลยีสารสนเทศ  
**มหาวิทยาลัย**: สถาบันเทคโนโลยีพระจอมเกล้าเจ้าคุณทหารลาดกระบัง  

---

## รายละเอียดของ Project: EmotiFace LED

### อุปกรณ์ที่ใช้

- **แผงไฟ LED WS2812B ขนาด 32x8**: อุปกรณ์หลักสำหรับการแสดงผล สามารถควบคุมการแสดงของพิกเซลแต่ละจุดได้อย่างอิสระ และแสดงสีได้ถึง 16,777,216 สีตามค่า RGB
- **Arduino**: ใช้ในการควบคุมแผง LED โดย Arduino ตัวที่ 1 ทำหน้าที่สั่งการให้แสดงผล และตัวที่ 2 ทำหน้าที่รับคำสั่งจากผู้ใช้
- **ระบบ MQTT Broker**: ช่วยในการสื่อสารระหว่าง Arduino ทั้งสองฝั่ง ให้การควบคุมทำงานได้อย่างต่อเนื่องและทันทีทันใด

### การทำงาน

แผง LED ขนาด 32x8 จะทำหน้าที่แสดงสีหน้าในรูปแบบต่าง ๆ ตามคำสั่งที่ส่งมาจากอุปกรณ์ควบคุม เช่น มือถือ หรืออุปกรณ์ที่เชื่อมต่อผ่าน Wi-Fi ระบบจะทำงานโดยใช้ไลบรารี FastLED บน Arduino และเชื่อมต่อข้อมูลผ่านโปรโตคอล MQTT ซึ่งทำให้ผู้ใช้สามารถควบคุมการแสดงผลได้อย่างง่ายดายและรวดเร็ว

### จุดเด่น

- **เปลี่ยนการแสดงผลได้หลากหลายรูปแบบ**: สามารถแสดงสีหน้าต่าง ๆ เช่น ยิ้ม โกรธ หรือเศร้า ได้อย่างง่ายดาย
- **ควบคุมได้แบบไร้สาย**: สามารถสั่งการและเปลี่ยนแปลงสีหน้าได้จากระยะไกลผ่าน Wi-Fi ซึ่งสะดวกต่อการใช้งานขณะ Cosplay
- **การแสดงสีได้หลากหลาย**: รองรับสีได้ถึง 16,777,216 สี ช่วยเพิ่มความสมจริงและชีวิตชีวาให้กับตัวละคร

### ประโยชน์ของ Project

- **ประยุกต์ใช้ในการแสดงหรือคอนเสิร์ต**: แผงไฟ LED สามารถใช้เป็นอุปกรณ์เสริมสำหรับการแสดงบนเวที สร้างความโดดเด่นให้กับผู้สวมใส่
- **สร้างสรรค์ในการ Cosplay**: เหมาะสำหรับการใช้งานที่ต้องการแสดงอารมณ์หรือบุคลิกภาพของตัวละครให้สมจริง
- **ใช้งานในเชิงการศึกษาและพัฒนาทักษะ**: เป็นโปรเจกต์พื้นฐานที่ใช้ในการเรียนรู้การเขียนโปรแกรมควบคุมฮาร์ดแวร์ และระบบ IoT รวมถึงการทำงานของระบบสื่อสารไร้สาย

---


