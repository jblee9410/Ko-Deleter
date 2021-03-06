# Ko-Deleter
Deletion based sentence compression with external language information
## Deleter를 통한 추출 기반 문장 요약
  1. Sentence chunking
  2. Make candidate sentences by deleting each chunk in original input sentence
  3. Scoring each candidate
  4. Selecting a candidate sentence

### Sentence chunking
  1. 구문 태그(Etri 의존 구문분석 API, TTA.KO-10.0853)
  2. 개체명 태그(Etri 개체명 인식 API, TTA.KO-10.0852)
  
  - 예시)
  <img src="https://user-images.githubusercontent.com/56908137/98515295-32fc9500-22ae-11eb-96c7-215ce18d8794.png" width="80%">
  
### Make candidate sentences
  1. 입력 문장에서 각 chunk를 삭제하여 후보 문장 생성
  
  - 예시)
  <img src="https://user-images.githubusercontent.com/56908137/98515297-34c65880-22ae-11eb-96ca-1373e229f66b.png" width="80%">

### Scoring each candidate
  1. AvgPPL
    - Masked Language Model scoring을 기반, 각 chunk의 중요도 판단

  <img src="https://user-images.githubusercontent.com/56908137/98509207-207d5e00-22a4-11eb-8dd0-d5a78140c807.PNG" width="80%">
  
  2. 각 chunk의 구문 태그, 개체명 태그마다 scoring weight를 두어 scoring에 외부 언어 지식 반영
