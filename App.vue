<template>
  <div>
  
    <div class="cims">
      <h2>
        고객정보 관리
      </h2>
    </div>
  
    <div class="All">
    <div class="containal">
  
    <ul id="usertop">
      <span>고객성명:</span>
      
      <li>
        <input type="text">
      </li>
  
      <div id="buttons">
        <li>
          <input type="button" value="조건 검색">
        </li>
        <li>
          <input type="button" value="전체 검색">
        </li>
      </div>
    </ul>
  
      <fieldset>
        <Customer :CustomerData="CustomerData"/>
        <!-- <p>
          <input name="customerName" type="radio"> 윤OO
        </p>
        <p>
          <input name="customerName" type="radio"> 강해라
        </p>
        <p>
          <input name="customerName" type="radio"> 나란다
        </p>
        <p>
          <input name="customerName" type="radio"> 담나라
        </p>
        <p>
          <input name="customerName" type="radio"> 라면다
        </p>
        <p>
          <input name="customerName" type="radio"> 박석일
        </p>
        <p>
          <input name="customerName" type="radio"> 이성경
        </p> -->
      </fieldset>
    </div>
  
    <!-------------------- 정보 입력 부분 ----------------------->
  
    <div class="infomation">
      <CustDetail :CustomerData="CustomerData" :cus_id="cus_id"/>
    <!-- <div class = "cust">
        <ul>
          <li>
            <label for="dop">**작성일자</label>
            <input type="text" id="dop" autofocus
            placeholder="몇월 몇일" required>
          </li>
          <li>
            <label for="name">*고객명</label>
            <input type="text" id="name" autofocus
            placeholder="이름" required>
          </li>
          <li>
            <label for="resident">*실명번호</label>
            <input type="text" id="resident" autofocus
            placeholder="번호" required>
          </li>
          <li>
            <label for="email">*E-mail</label>
            <input type="text" id="email" autofocus
            placeholder="이메일을 입력하세요" required>
          </li>
          <li>
            <label for="number">전화번호</label>
            <input type="text" id="number" autofocus
            placeholder="연락처" required>
          </li>
          <li>
            <label for="phone">*핸드폰번호</label>
            <input type="text" id="phone" required>
          </li>
          <li>
            <label for="job">*직업</label>
            <input type="text" id="job" required> 
          </li>
          <li>
            <label for="address">주소</label>
            <textarea cols="20" rows="3"></textarea>
          </li>
          </ul>
        </div> -->
          <hr>
          <div class="manager">
            <ul>
              <li>
                <label for="manager">관리담당자</label>
                <input type="text" id="manager" required>
                <button class="button_img"></button>
              </li>
              <li>
                <label for="department">**부서</label>
                <input type="text" id="department" required>
              </li>
              <li>
                <label for="position">**직위</label>
                <input type="text" id="position" required>
              </li>
              <li>
                <label for="number2">**연락처</label>
                <input type="text" id="number2" required>
              </li>
            </ul>
        </div>
      </div>
  
    <!-------------------- 상담 내역 부분 ----------------------->
  
    <div class="details">
        <h3>상담내역:</h3>
        <div class="detail_box">상담내용 들어갈 자리</div>
  
        <div>
          <button class="btn register">등록</button>
          <button class="btn update">변경</button>
          <button class="btn delete">삭제</button>
          <button class="btn new">신규</button>
        </div>
  
        <div>
          <button class="btn inquiry">고객조회</button>
        </div>
  
        </div>
    </div>
  </div>
  </template>

  <script>  
  import Customer from './components/Customer.vue';
  import CustomerData from './assets/customer.js';
  import CustDetail from './components/CustDetail.vue';

  export default {
    name : 'App',
    data() {
      return {
        CustomerData: CustomerData,
        cus_id : 3,
        
      }
    },
    
    components: {
      Customer,
      CustDetail,
    },
  }
  </script>
  
  <style>
  
    .All {
      background-color:rgb(245, 244, 244);
      border: solid 2px black;
      height: 1000px;
    }
  
    .cims {
      color: white;
      background-color:deepskyblue;
      height: 50px;
      border-top: solid 2px black;
      border-left: solid 2px black;
      border-right: solid 2px black;
      padding-left: 10px;
      padding-bottom: 20px;
    }
  
    .containal {
      float: left;
    }
  
    fieldset {
      max-width: 150px;
      height: 500px;
      background-color: white;
      font-size: 20px;
      font-weight: 500;
    }
  
    #usertop {
      padding-left: 0px;
      font-weight: bold;
    }

    #usertop span, fieldset {
      margin-left: 20px;
    }
  
    #buttons input {
      width: 175px;
      height: 30px;
      background-color: deepskyblue;
      color: white;
      font-size: 20px;
      font-weight: bold;
      border-radius: 5px;
    }
  
    input[type="text"] {
      width: 170px;
      height: 30px;
    }
  
    span {
      font-size: 20px;
    }
  
    * {
      list-style: none;
    }
    /* ------------ 정보입력 ------------ */
    .infomation {
      float: left;
      margin-top: 40px;
    }

    ul {
      list-style: none;
      padding-left: 0;
    }

    ul li {
      margin: 20px;
    }

    li label {
      width: 120px;
      line-height: 36px;
      float: left;
      font-weight: bold;
      text-align: right;
      margin-right: 10px;
    }
    
    .manager ul li:first-child { 
      position: relative;
      display: flex;
    }

    .manager ul li:first-child input { 
      width: 100%;
    }

    .manager ul li:first-child button {
      background: url(./assets/search.png) no-repeat;
      background-size: cover;
      width: 30px;
      height: 30px;
      border-width: 0;
      position: absolute;
      right: 5px;
      top: 3px;
    }
  
    /* ------------ 상담내역 ------------ */
  
    .details {
      float: left;
      margin-left: 20px;
    }
  
    .details h3 {
        margin-left: 10px;
      }

    .detail_box {
      width: 500px;
      height: 565px;
      margin: 10px;
      padding: 5px;
      border: 1px solid gray;
      border-radius: 1px;
    }

    .btn {
      max-width: 150px;
      height: 40px;
      width: 123px;
      align-items: center;
      font-size: 20px;
      font-weight: 700;
      color: white;
      background-color: deepskyblue;
      text-decoration: none;
      cursor: pointer;
      margin-left: 7px;
      margin-right: auto;
      margin-bottom: 10px;
      border-radius: 5px;
      transition: 0.5s;
    }
  
    .inquiry {
      background-color: rgb(228, 195, 152);
      color: black;
    }

  </style>
