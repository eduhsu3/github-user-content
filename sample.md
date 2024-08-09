# Vitcoin
 
<br><br>

## 프로젝트 소개

-   가상화폐 현황과 차트, 뉴스를 볼수 있는 웹사이트

<br>

## 프로젝트 기간

-   21.10.15 ~ 21.10.25
    <br>

## 사용된 기술 & 라이브러리

-   React
-   Redux,Redux-toolkit
-   Rapid api
-   chart.js
-   Ant Design(ui)
-   그외 moment,millify,num-to-korean,uuid 사용
    <br>

## 프로젝트 구현

1. Open Api

    - coinRaking : 가상화폐의 현황과 가격변동등을 알 수 있습니다.
    - exchangeRate : 달러 기반 데이터를 원화로 바꾸기 위해 사용했습니다.
    - bing news : 실시간으로 기사를 확인할 수 있도록 뉴스검색을 구현했습니다.

2. Redux RTK query로 data Fetch 구현

-   redux store

```javascript
export default configureStore({
    reducer: {
        [cryptoApi.reducerPath]: cryptoApi.reducer,
        [exchangeApi.reducerPath]: exchangeApi.reducer,
        [newsApi.reducerPath]: newsApi.reducer,
    },
});
```

-   Data Fetch(coinRaking)

```javascript
const cryptoApiHeaders = {
    'x-rapidapi-host': 'coinranking1.p.rapidapi.com',
    'x-rapidapi-key': '130cffa3bbmsh7d5ad1d7d41daefp183e2ejsn0e69e9df3cef',
};

const baseUrl = 'https://coinranking1.p.rapidapi.com';

const createRequest = (url) => ({ url, headers: cryptoApiHeaders });

export const cryptoApi = createApi({
    reducerPath: 'cryptoApi',
    baseQuery: fetchBaseQuery({ baseUrl }),
    endpoints: (builder) => ({
        getCryptos: builder.query({
            query: (count) => createRequest(`/coins?limit=${count}`),
        }),
        getCoin: builder.query({
            query: (id) => createRequest(`/coin/${id}`),
        }),
        getCryptoHistory: builder.query({
            query: ({ coinId, timePeriod }) => createRequest(`/coin/${coinId}/history/${timePeriod}`),
        }),
        getExchanges: builder.query({
            query: () => createRequest('/exchanges'),
        }),
    }),
});

export const { useGetCryptosQuery, useGetCoinQuery, useGetCryptoHistoryQuery, useGetExchangesQuery } = cryptoApi;
```

<br>

## 웹사이트 링크

[구경하기](https://vitcoin.netlify.app/)

## 구현 영상

![나의 동영상1](https://user-images.githubusercontent.com/70016523/138905268-7906a1f4-cdd6-4188-86c1-7c728d0e07f7.gif)

# level1

## lever2

### lever3

줄바꿈을 하려면 문장 뒤에 스페이스 두번  
들어 가야 줄바꿈 됩니다.

This is _Italic_

This is **Bold**

# 인용문구

> Lev 1.
> Lev 1, Continue.
>
> > Lev 2.
> > Lev 2, Continue.
> >
> > > Lev 3

# 기호 목록

1. 내 이름은 박병
2. 내 이름은 TH
3. 내 이름은 TS

-   기호로 -, \*, + 를 사용할 수 있다.
-   기호는 또 이렇게
-   여기에 문장이
    -   2단계 - 3단계
    -   2단계 계속

# code 입력 두가지 방법

```
function names(){

}
```

    function names(){

    }

# 이미지

![대체텍스트](https://cdn.pixabay.com/photo/2024/08/04/09/02/cat-8943928_960_720.png)

# 링크

[네이버링크](https://www.naver.com)
