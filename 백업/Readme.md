# 강수량 기후통계데이터를 이용한 하천범람 예측
## 분석할 내용
- 하천설계기준 및 하천범람기록에 대한 데이터를 조사하여 강수량 통계와의 연관성을 분석한다.
- 현재 일기예보에 기입된 시간당 강수량 및 현재 시기(계절, 월 등)에 대해 일일 총 강수량을 예측하고, 이를 이용하여 주변 하천범람가능성을 예측한다.

## 사용할 데이터
### 강수량 기후통계데이터(기상청 API)
- API를 이용하여 특정 지역의 일/월/연도 별 강수기록을 분석한다.
- 분석 내용을 토대로 주변 하천의 제방의 높이, 평시 수면높이 등을 조사하여 하천범람 가능성을 분석할 예정이다.

![강수API1](media/강수API1.png)  
![강수API2](media/강수API2.png)  
- RN_DSUM: 일합계강수량(mm)
- RN_MAX_10M: 10분최다강수량(mm)  
(10분최다강수량이란 하루동안의 가장 많이 내린 10분강수량 값을 의미)
- RN_MAX_1HR: 1시간최다강수량(mm)
- RN_MAX_6HR: 6시간최다강수량(mm)
- 출처: [https://apihub.kma.go.kr/](https://apihub.kma.go.kr/)  
(출처가 동적 페이지로 되어 있어, 지상관측>기후통계 경로의 '14. 강수량 기후통계데이터 조회'API를 이용함을 밝힙니다.)

### 하천설계기준
- 국토교통부에서 배포한 자료는 해당 깃허브의 data 폴더에 있습니다.  
출처: [https://www.molit.go.kr/USR/I0204/m_45/dtl.jsp?gubun=&search=&search_dept_id=&search_dept_nm=&old_search_dept_nm=&psize=10&search_regdate_s=&search_regdate_e=&srch_usr_nm=&srch_usr_num=&srch_usr_year=&srch_usr_titl=&srch_usr_ctnt=&lcmspage=1&idx=15899](https://www.molit.go.kr/USR/I0204/m_45/dtl.jsp?gubun=&search=&search_dept_id=&search_dept_nm=&old_search_dept_nm=&psize=10&search_regdate_s=&search_regdate_e=&srch_usr_nm=&srch_usr_num=&srch_usr_year=&srch_usr_titl=&srch_usr_ctnt=&lcmspage=1&idx=15899)
- 자료가 다소 많으므로, 자세한 내용은 조사예정

### 기타 수집예정 자료
- 하천에 대한 자료(csv, API 등)
- 기존의 하천범람에 대한 기록(csv)

### 기타
#### 호우피해 이력기록
[https://bd.kma.go.kr/kma2020/fs/preventionSelect1.do?pageNum=5&menuCd=F050401000#](https://bd.kma.go.kr/kma2020/fs/preventionSelect1.do?pageNum=5&menuCd=F050401000#)
- 이 내용도 활용을 고려하였으나, 해당 내용은 2016년 이후 업데이트가 되지 않았다.


## 프로젝트 범위
- API 및 csv를 이용한 데이터 수집 및 가공
- 판다스 라이브러리를 이용하여 통계데이터 분석
- matplot 라이브러리를 이용한 데이터 시각화
- 머신러닝/딥러닝을 이용한 일일 총 강수량 예측 및 하천 범랑가능성 예측