# GeoJSON

- 다양한 지리 데이터 구조를 JSON 형식으로 표현하기 위한 포맷
- 해당 표준 포맷 형식을 이용해서 애플리케이션에서 지리적 데이터를 주고받을 때 유용하다.
- [RFC 7946 표준](https://www.rfc-editor.org/rfc/rfc7946)

```json
{
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [126, 37] // longitude, latitude
  },
  "properties": {
    "name": "<name>"
  }
}
```

# 사전 지식

- 위도 : 지구상에서 적도(지구를 반으로 가르는 선)를 기준으로 북쪽과 남쪽으로 얼마나 떨어져 있는지 나타내는 위치. 0° ~ 90°
  - 적도 : 지구를 반으로 가르는 선. 0°
  - 북위 : 북쪽으로 올라갔을 때 표현식
  - 남위 : 남쪽으로 올라갔을 때 표현식
- 경도 : 지구상에서 본초 자오선을 기준으로 동쪽과 서쪽으로 얼마나 떨어져 있는지 나타내는 위치. 0° ~ 180°
  - 본초 자오선 : 영국 그리니치의 그리니치 천문대를 지나는 자오선. 0°
  - 서경 : 서쪽으로 갔을 때 표현식
  - 동경 : 동쪽으로 갔을 때 표현식

# GeoJSON Data Type

- `Feature`, `FeatureCollection`
- `Feature`는 지리 정보를 나타내는 주체이다. geometry와 properties를 가지며 지리 형태와 좌표, 특징을 가진다.
- `FeatureCollection`은 `Feature`의 집합이라고 생각하면 된다.

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [102.0, 0.5]
      },
      "properties": {
        "prop0": "value0"
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "LineString",
        "coordinates": [
          [102.0, 0.0], [103.0, 1.0], [104.0, 0.0], [105.0, 1.0]
        ]
      },
      "properties": {
        "prop0": "value0",
        "prop1": 0.0
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
            [100.0, 0.0], [101.0, 0.0], [101.0, 1.0],
            [100.0, 1.0], [100.0, 0.0]
          ]
        ]
      },
      "properties": {
        "prop0": "value0",
        "prop1": { "this": "that" }
      }
    }
  ]
}
```

# Geometry Type

## 기본 형태

![geometry primitives](https://user-images.githubusercontent.com/50051656/198679232-bbd19304-1b92-4921-8de5-25e79ce961e9.png)

## 복잡한 형태

![multipart geometries](https://user-images.githubusercontent.com/50051656/198679224-f930ad6e-8423-4d69-a5f9-8600945906dc.png)

# GeoJSON visualization

- https://geojson.io/

# Reference

- https://ko.wikipedia.org/wiki/GeoJSON
- https://ko.wikipedia.org/wiki/%EC%9C%84%EB%8F%84
- https://ko.wikipedia.org/wiki/%EA%B2%BD%EB%8F%84
- https://ko.wikipedia.org/wiki/%EB%B3%B8%EC%B4%88_%EC%9E%90%EC%98%A4%EC%84%A0
