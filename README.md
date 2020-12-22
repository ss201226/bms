# bms
맨 처음 main에서 선택받기 
1번 계좌개설 선택
	->은행, 이름, 비밀번호(매개값으로 넘겨줌) 입력받아서 Manager의 join메소드 호출
	->m.join() : 계좌 랜덤한 4자리 숫자로 만들기 ->중복검사(중복검사를 위한 변수 사용)
	->중복검사 실패->while문 다시 반복 / 중복검사 성공->while문 탈출
	->Main case 1: break; 

2번 로그인 선택
	-> 계좌번호, 비밀번호 입력받아서 login() 메소드 호출
	->m.login(): 계좌개설과 같이 반복. 계좌번호,비밀번호 같으면 로그인 성공
	->로그인 성공시 그 객체 return / 실패시 null return
	->Main case 2: session(로그인한 유저의 정보)이 null이 아니라면 로그인 성공
	->loginView() 메소드 호출
	->v.loginView(): 로그인 된 상태에서 입금,출금,계좌조회 등 입력받기
	
	v.loginView()
		입금: 입금할 금액 money에 입력받아서 session의 deposit메소드 호출
		출금: 출금할 금액 money에 입력받아서 session의 withdraw메소드 호출
		계좌조회: session.show() 호출
		송금: 송금할 계좌, 금액 입력받은 뒤 findTarget()메소드 호출
		 -> m.findTarget(): 계좌일치하는 회원찾아서 그 값 리턴 없으면 null 리턴
		비밀번호 재설정: pw 입력받아서 동일한 pw가 있다면 newPw 입력받기
		 -> 입력받은 후 session에 null을 대입해 로그아웃 상태 만들기
		로그아웃: session에 null 넣어주기 

3번 비밀번호찾기 선택
	-> 계좌번호, 이름 입력받아서 findPw() 메소드 호출 
	->m.findPw(): 지정된 문자열 중에 6자 랜덤하게 설정해서 newPw에 넣어주기 
	->처음 account,pw와 받아온 account,pw와 일치하는지 확인  
	->일치하면 pw에 newPw 대입하고 return; 일치하지 않으면 null reuturn;
	->Main case 3: newPw가 null이 아니라면 비밀번호 재설정 완료
			      
