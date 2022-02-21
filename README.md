# Data Analysis on Naver Webtoon Reviews and Comments
## 네이버 웹툰 복학왕 평점/리뷰 분석

![image](https://user-images.githubusercontent.com/38115693/154954551-58555fbd-6ead-4f44-b27e-c43880a5d4ec.png)

## 프로젝트 배경
- 네이버 웹툰의 재미
- **평점과 댓글 내용간 유의미한 상관관계** 존재 여부에 대한 궁금증
- **저조한 평점 발생 원인** 궁금

## 웹툰 <복학왕> 선정 이유
- 작가의 부정적 이슈, 작품 퀄리티에 따른 여론이 평점과 댓글에 가장 잘 드러나는 작품
- 다양한 이슈와 논란이 있었던 웹툰이며 낮은 평점의 빈도수가 높았던 웹툰

## 프로젝트 내용
- **데이터 수집**
  a. 제목, 회차별 등록일, 평점, 베스트댓글 데이터 수집
  b. **Requests와 BeautifulSoup 사용하여 크롤링**
  c. 댓글 데이터 수집은 용량 문제로 인하여 베스트댓글 15개만 가져오기로 결정
- **데이터 분석**
  a. **평점이 낮은 회차의 원인을 사회적 이슈 및 논란을 확인하여 분석**
  b. 평점 8.00 미만 회차에 대한 원인 분석
  c. 베스트댓글 속 특정 단어들을 키워드로 활용하여 **관련 기사 데이터 수집 및 분석**

## 문제 및 해결
- **베스트댓글**
  - 베스트댓글 데이터는 크롤링이 되지 않음
  - 별도의 URL 존재하고, 트래픽 시간차가 존재하는 것으로 보아 댓글들이 동적으로 반응하여 렌더링 된다고 판단
  - Request로는 크롤링을 할 수 없어, Selenium을 사용하여 동적 크롤링 수행
- **클린봇의 방해**
  - 크롤링간 특정 구간에서 지속적인 오류가 발생하여, 확인해 보니 클린봇에 의한 숨겨진 댓글들 존재
  - 이러한 댓글들은 클래스(class) 이름이 다른 것을 확인
  - try, except를 주어 코드 수정 후 다시 크롤링 진행 

## 분석 결과
- 평점이 낮은 회차들에 부정적인 댓글들 존재
- **평점이 낮은 회차들의 부정적인 댓글들의 키워드를 활용하여 관련 기사를 수집하고 분석한 결과, 평점이 낮은 회차들에 대해선 사회적 논란이 있었음**
