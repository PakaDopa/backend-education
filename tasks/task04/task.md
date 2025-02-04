# Task4

- 2020\-08\-05 (WED)
- 주제: 일반 크롤링
- 성서봇은 대부분의 정보를 실시간 크롤링을 통해 가져오기 때문에, 크롤링 코드를 능숙하게 작성할 수 있어야 합니다.

## 배우는 내용

1. 하나의 페이지에서 단서를 얻어, 다음 크롤링 대상을 결정합니다.

## 사전 요구사항

1. `pip`를 이용해 `requests` 패키지 설치
2. `pip`를 이용해 `beautifulsoup4` 패키지 설치

## 태스크

[교내 대학생활 공지사항](https://www.bible.ac.kr/ko/life/notice) 정보를 가져오는 것에서 한 스텝 더 나가보겠습니다.

[교내 대학생활 공지사항](https://www.bible.ac.kr/ko/life/notice) 페이지에서 각 공지사항 글의 정보를 가져오면 됩니다.

가져와야할 정보는 다음과 같습니다.

1. 공지사항 글의 url
2. 제목
3. 작성자
4. 작성일자
5. 본문

`get_notice_articles` 의 `page_num` 파라미터는 페이지 번호를 의미합니다.![]()

```python
from typing import List


def get_notice_articles(page_num: int = 1) -> List[List[str]]:
    """코드 작성"""
```

**반환 예시:**

```python
>>> get_notice_articles(1)  # 공지사항 1페이지의 모든 공지사항 정보를 가져온다.
[
    ["https://www.bible.ac.kr/ko/life/notice/view/46624?p=1", "[수업] 2020-2학기 코로나19 대비 학사운영 방안", "유미나", "2020-07-24 19:18:46", "코로나19 대비 2020-2학기 학사운영과 관련하여 교무위원회(7/22) 의결사항을 다음과 같이 알려드립니다. 1. 수업운영 원칙..."],
    ["https://www.bible.ac.kr/ko/life/notice/view/46603?p=1", "[수업] 2020-2학기 수강신청 안내 (수정 7/24)", "유다운", "2020-07-17 11:56:35", "2020-2학기 수강신청을 아래와 같이 안내드립니다. 아래 내용을 꼭! 숙지하신 후 수강신청을 진행하시기 바랍니다...."],
    ...
]
```

본문은 너무 길어서 생략하였으나, 실제로 가져올 때는 모든 본문을 가져와야합니다.

단, 텍스트 글만 가져와야 하고, 줄바꿈 문자(`\n` 또는 `\r\n`)는 공백 문자() 로 치환하세요.

> 정보를 가져올 시 select() 또는 find() 메서드를 사용해보세요.
> 커밋메세지를 자세히 써서 제출하세요.
