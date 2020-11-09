# Ko-Deleter
Deletion based sentence compression
## Deleter를 통한 추출 기반 문장 요약
  1. Sentence chunking
  2. Make candidate sentences by deleting each chunk in original input sentence
  3. Score each candidate
  4. Select a candidate sentence

### Sentence chunking
  1. 구문 태그(Etri 의존 구문분석 API, TTA.KO-10.0853)
  2. 개체명 태그(Etri 개체명 인식 API, TTA.KO-10.0852)
  
  예시)
  ![sentence chunking](https://user-images.githubusercontent.com/56908137/98515295-32fc9500-22ae-11eb-96c7-215ce18d8794.png)
### Make candidate sentences
  1. 입력 문장에서 각 chunk를 삭제하여 후보 문장 생성
  
  ![candidate sentences](https://user-images.githubusercontent.com/56908137/98515297-34c65880-22ae-11eb-96ca-1373e229f66b.png)

  - Masked Language Model scoring을 기반으로 문장의 각 토큰의 중요도를 판단

![AvgPPL](https://user-images.githubusercontent.com/56908137/98509207-207d5e00-22a4-11eb-8dd0-d5a78140c807.PNG)

