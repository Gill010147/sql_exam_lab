# sql_exam_lab
mysql & oracle의 기초 sql문 관련한 문제입니다 ☺️

현재 oracle 예제 DB상태일때를 가정하여 제작되었습니다.  
사원 테이블 : emp | 부서 테이블 : dept

---
# 👥팀소개
<div align="center">
  
|신기범|김동민|황병길|장송하|
|:---:|:---:|:---:|:---:|
|[shin-kibeom](https://github.com/shin-kibeom)|[kddmmm](https://github.com/kddmmm)|[Gill010147](https://github.com/Gill010147)|[jangongha](https://github.com/songhajang)|
|<img width="200" height="250" alt="Image" src="https://github.com/user-attachments/assets/25e044a7-b6b2-4309-b731-0e472617b4d7" />|<img width="200" height="250" alt="Image" src="https://github.com/user-attachments/assets/1363ce0d-5abe-4f0c-b3f5-bbbd48924ac9" />|<img width="200" height="250" alt="Image" src="https://github.com/user-attachments/assets/99ef8771-e061-4b07-b587-95d76c3e97da" />|<img width="200" height="250" alt="Image" src="https://github.com/user-attachments/assets/158494bb-76c3-41b3-b457-213f6add7b3b" />|
  
</div>


### 📌 1. 상사번호(7839)인 사원명(ename)을 입사날이 오래된 순으로 조회하기  
상사번호: mgr , 사원명: ename, 입사날: hiredate 으로 가정한다.

<details>
<summary>✅정답 보기</summary>
  
```
SELECT ename AS 사원명, hiredate AS 입사일
FROM emp
WHERE mgr = 7839
ORDER BY hiredate ASC;
```

</details>

---

### 📌 2. 연봉이 30000 이상인 사원 이름 출력하기  
급여: sal, 커미션: comm, 사원명: ename 으로 가정한다.

<details>
<summary>✅정답 보기</summary>
  
```
SELECT ename AS 사원명, sal12 AS 연봉
FROM emp
WHERE sal12 >= 30000;
```

</details>

---

### 📌 3. 직업이 salesman인 사람 중 커미션이 있는 사람의 사원명, 사원번호, 커미션 출력하기  
사원명: ename , 직업: job, 사원번호: empno, 커미션: comm 으로 가정한다.

<details>
<summary>✅정답 보기</summary>
  
```
SELECT ename AS 사원명, empno AS 사원번호, comm AS 커미션
FROM emp
WHERE job = 'SALESMAN' AND comm > 0;
```

</details>

---

### 📌 4. 이름에 A가 들어가고 1981년 입사한 같은 부서 동기의 사원명, 직업, 입사날, 부서번호 출력하기  
사원명: ename , 직업: job, 입사날: hiredate, 부서번호: deptno 으로 가정한다.

<details>
<summary>✅정답 보기</summary>
  
```
SELECT ename AS 사원명, job AS 직업, hiredate AS 입사일, deptno AS 부서번호
FROM emp
WHERE deptno = 30
AND hiredate BETWEEN TO_DATE('1981-01-01', 'YYYY-MM-DD') AND TO_DATE('1981-12-31', 'YYYY-MM-DD')
AND ename LIKE '%A%';
```

</details>
