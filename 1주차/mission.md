# 한글 자연어 → SQL 프롬프트 엔지니어링 연습 가이드

## 📦 1. DB 스키마 (SQL)

```sql
CREATE TABLE Users (
    user_id INT PRIMARY KEY,
    username VARCHAR(255),
    email VARCHAR(255),
    created_at DATETIME
);

CREATE TABLE Orders (
    order_id INT PRIMARY KEY,
    user_id INT,
    product_name VARCHAR(255),
    quantity INT,
    order_date DATETIME,
    FOREIGN KEY (user_id) REFERENCES Users(user_id)
);

CREATE TABLE Products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(255),
    price INT,
    stock INT
);

CREATE TABLE Reviews (
    review_id INT PRIMARY KEY,
    user_id INT,
    product_id INT,
    rating INT,
    comment VARCHAR(255),
    review_date DATETIME,
    FOREIGN KEY (user_id) REFERENCES Users(user_id),
    FOREIGN KEY (product_id) REFERENCES Products(product_id)
);
```

---

## 📖 2. 자연어 질문 (난이도 및 유형별 구성)

### 📌 단순한 질문 (8개)

1. 가장 최근에 가입한 사용자 5명을 알려줘.
2. 재고가 10개 이하인 상품들을 찾아줘.
3. 평균 평점이 4 이상인 상품 목록을 알려줘.
4. 오늘 작성된 리뷰 수를 알려줘.
5. 총 주문 수를 알려줘.
6. 사용자별 주문 수를 집계해줘.
7. 재고가 가장 많은 상품을 알려줘.
8. 평점이 가장 높은 리뷰를 알려줘.

### 📌 복합 질문 (6개)

9. 최근 7일 동안 가장 많이 팔린 상품을 알려줘.
10. 사용자별 평균 평점을 알려줘.
11. 리뷰가 가장 많은 상품을 알려줘.
12. 주문이 없는 사용자를 찾아줘.
13. 상품별 총 주문 수량을 알려줘.
14. 사용자별 최근 주문 정보를 알려줘.

### 📌 어려운 복합 질문 (11개)

15. 리뷰가 2개 이상이고 평균 평점이 4 이상인 상품을 알려줘.
16. 최근 7일 동안 주문된 상품 중 재고가 부족한 상품을 찾아줘.
17. 주문이 없는 사용자 중 리뷰를 남긴 사용자를 찾아줘.
18. 사용자별로 가장 최근에 작성한 리뷰를 알려줘.
19. 사용자별 총 지출 금액이 가장 높은 사용자를 알려줘.
20. 평균 평점이 가장 높고 주문 수량이 가장 많은 상품을 알려줘.
21. 재고가 0개 이상이고, 주문 수량이 0보다 작은 상품을 찾아줘.
22. 리뷰 수가 적당히 많은 상품을 알려줘.
23. 이메일이 gmail.com이고 주문한 상품이 Smartphone인 사용자를 알려줘.
24. 가입일이 미래인 사용자를 찾아줘.
25. 상품 이름이 이메일인 상품을 찾아줘.

---

## 🚀 추천 사용법

1. 제로샷 → 아무 도움 없이 시도
2. 원샷/투샷 → 예시 참고하면서 개선
3. 생각 사슬 → 풀이 과정을 적어가며 시도
4. 자기 일관성 → 여러 해답 중 가장 일관된 선택
5. 선택 추론 → 옵션형 문제로 선택 후 SQL 작성
6. 난이도 조절 + 탈옥 케이스로 심화 트레이닝

---

