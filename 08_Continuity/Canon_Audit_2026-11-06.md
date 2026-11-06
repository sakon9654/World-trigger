---
id: CANON-AUDIT-2026-11-06
type: audit_report
tier: source_canon
status: approved
audit_date: 2026-11-06
scope: roster_rank_trigger_stats_side_effect
audit_method: source_cross_check
---
# Canon database audit — 2026-11-06

## หลักการ
ข้อมูลในไฟล์ source_canon แบ่ง 3 ชั้น:
1. **verified_source** = ตรงกับแหล่งอ้างอิงที่ตรวจได้ในรอบนี้ (อาจยังเป็นแหล่งรอง)
2. **time_qualified** = เป็นจริงสำหรับ snapshot ช่วงเวลานั้น ไม่ได้แปลว่าเป็น canon-cutoff snapshot
3. **unverified** = ยังไม่พอใช้อ้างเป็นความจริงแน่นอนในฉาก; ห้ามให้ AI เติมส่วนที่หายเอง

ใช้หลักฐานปฐมภูมิก่อน: สำนักพิมพ์ Shueisha (สารบัญหนังสือ) > manga/BBF ที่มีหน้าอ้างอิง > Wiki ที่ถอดข้อมูลและโยงหน้า > wiki claims ไม่มีหน้าอ้างอิง

## ผลตรวจพบและการแก้ไข

| ID | Severity | Finding | Resolution |
|---|---|---|---|
| AUD-001 | HIGH | คำว่า "มี A-rank 9 ทีม" ถูกเข้าใจผิดเป็น A-rank #9 ทั้งที่มีอันดับ #1 ถึง #8 และ Tamakoma First ไม่เข้าร่วม Rank Wars | ปรับ [[Expanded_Roster]] ให้ระบุ rank #1–#8 + ทีมไม่จัดอันดับ |
| AUD-002 | HIGH | B-rank squad ranks ช่วง BBF 2016 ผสมกับอันดับหลัง Rank Wars; ใน BBF #15 Matsushiro, #16 Ebina, #17 Chano, #18 Tokiwa, #19 Hayakawa, #20 Yoshizato, #21 Mamiya | ปรับป้ายเวลาและระบุแหล่ง Shueisha ใน [[Expanded_Roster]] |
| AUD-003 | HIGH | Osamu Trigger loadouts รวม Trigger ของหลายรอบจนตีความว่าเป็นชุดเดียว; รอบ 8 ย้าย Spider ไป Sub, Hound ไป Sub, Bagworm ไป Main | แก้ [[Agent_Loadouts]] ใส่ Main/Sub snapshots ราวด์ 2–4, 5–7, 8 |
| AUD-004 | HIGH | source-canon S-rank ผูกกับ Black Trigger เป็น main; ความเป็น S-rank ของคุกะในนิยายหลังรักษายังต้องมีกฎหรือเหตุผลของผู้เขียน | แยกเป็น hypothetical/future continuity, ไม่เปลี่ยนตามต้นฉบับโดยพลการ |
| AUD-005 | MEDIUM | Side Effect grade A/B/C/S เป็นระดับชนิดของพลัง ไม่ใช่อันดับ Border; คุกะเห็นการโกหกจากคำพูดที่ผู้พูดรู้อยู่แล้วว่าโกหก ไม่อ่านใจและไม่เห็นจากตัวหนังสือ | บันทึกแหล่ง manga Q&A และข้อจำกัดใน [[Side_Effects]] |
| AUD-006 | MEDIUM | BBF ค่าสถานะจากหน้า wiki ถอดมาจากหนังสือและบางค่าจาก manga ภายหลัง; Trion ไม่ใช่ Combat Power และ Operator มีคนละสเกล | [[BBF_Parameters]] ยังเป็น working transcription; ห้ามใช้แทน T+4Y |
| AUD-007 | MEDIUM | รายการ Trigger Users แสดง "เคยใช้" ไม่ได้ระบุ Main/Sub และบางกรณีเป็น former/prototype/anime-only | [[Expanded_Agent_Triggers]] ไม่ถือเป็น full equipped loadout |
| AUD-008 | HIGH | Canon cutoff ของผู้เขียนยังระบุเป็นคำบรรยายเหตุการณ์ (กลุ่ม B ชั้นบนในการสอบรอบสุดท้าย) ยังไม่สามารถผูกเลข chapter | ห้ามตีเลขบทเอง; ทุกข้อมูลหลัง cutoff ต้องระบุ proposed until validated |

## จุดตรวจยืนยัน
- Official Shueisha BBF contents: https://books.shueisha.co.jp/items/contents.html?jdcn=08880704870809315501 — ขอบเขต A-rank #1–#8, lower B-rank ใน BBF
- World Trigger wiki squad overview: https://worldtrigger.fandom.com/wiki/Squads
- Border rank definitions: https://worldtrigger.fandom.com/wiki/Border
- S-rank main Black Trigger: https://worldtrigger.fandom.com/wiki/Trigger
- BBF stats transcribed: https://worldtrigger.fandom.com/wiki/Border_Briefing_File/Character_Stats
- Trigger users: https://worldtrigger.fandom.com/wiki/Border_Briefing_File/Trigger_Users
- Osamu per-round configurations: https://worldtrigger.fandom.com/wiki/Osamu_Mikumo/Abilities
- Side Effects including source references / volume 23 Q&A: https://worldtrigger.fandom.com/wiki/Side_Effect
- Kusakabe squad confirmation: https://worldtrigger.fandom.com/wiki/Kusakabe_Squad
- Katagiri squad confirmation: https://worldtrigger.fandom.com/wiki/Katagiri_Squad

## Outstanding validation queue
- [ ] ยืนยัน chapter cutoff จากคำอธิบายของผู้เขียน
- [ ] ตรวจ A/B squad รายคนจากหน้าอ้างอิงเดิมและมังงะว่าไม่มีชื่อ/ตำแหน่งผิด รวมถึง time-dependent ranks
- [ ] ตรวจ Main/Sub 8 สล็อตครบทุกคนจาก profiles ไม่ใช่ Trigger Users index
- [ ] ตรวจ rank บุคคลว่ามีตัวเลข/เวลาชัดเจน ไม่ใช่อันดับทีม
- [ ] ตรวจ BBF Parameters ทุกแถวเทียบแหล่งต้นฉบับ โดยเฉพาะรายการ partial และ stat ข้ามยุค
- [ ] เพิ่ม provenance เป็น page/chapter ต่อ cell หรือแต่ละ profile เมื่อทำ character records
- [ ] หยุดใช้ข้อมูล Anime-only ในเส้น canonical manga
- [ ] นับชุดข้อมูล original vs hypothetical/future แยกจากกันอย่างเข้มงวด

## Note for narrative AI
Read this audit before referring to source canon. Fact with `status:draft` should be phrased as *unverified reference*, not established canon; this report confirms only explicitly listed findings, **not** that the whole database is fully correct.
