## 2. 분석 목표 설정 (지표 설정)

1. 스타벅스 지점 100m 반경 내 이디야 지점이 **다수** 존재한다면 근처 입점으로 판단 <br>
    - 구별로  <br>

    - 근처 입점률 = 스타벅스 지점 100m 반경 내 존재하는 이디야 지점 / 전 이디야 지점
    - folium.Circle과 folium.Marker 사용으로 매장 데이터 시각화
    - Choropleth 사용으로 근처 입점률이 높은 지역 시각화  
<br>

2. 스타벅스와 이디야 매장 도로명 주소를 활용한 입지 전략 검증. <br>
도로명 주소 구분은 '대로'와 '로'를 기준으로, 이에서 분기된 '길'과 '번길'로 세분화 <br>
스타벅스는 허브 앤 스포크 전략에 따라 '대로'와 '로' 주소의 지점 비율이 높을 것, <br>
이디야는 포인트 투 포인트 전략에 '길'과 '번길' 주소의 지점 비율이 높을 것으로 예상 <br>

    - 각 지역의 비율을 따른 전략 비율 정의 (단순 정의)
    - 허브 앤 스포크 비율 = '대로', '로' 주소 갯수 / 전체 주소 갯수
    - 포인트 투 포인트 비율 = '번길', '길' 주소 갯수 / 전체 주소 갯수
    - 이디야 매장의 허브 앤 스포크 비율이 50% 이상인 지역 중, 스타벅스의 같은 비율과 차이가 5% 이하인 경우 '옆자리 전략' 적용 지역으로 표시
    - DataFrame 활용 구 별 주소 비율 분석
    - Choropleth를 활용 지역 시각화