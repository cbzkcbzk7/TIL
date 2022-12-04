## 원격 프로그램 실행

### 원격 프로그램 실행

    - 브라우저에서 ip주소:port = URL 로 호출하면 Tomcat이 프로그램을 실행시키는데,
    다른 컴퓨터의 프로그램을 아무거나 실행시키면 안됨으로 2가지 사전작업이 필요함.
    1. 프로그램 등록
    2. URL과 프로그램을 연결

```java
@Controller //1. 프로그램 등록
public class Hello {

   @RequestMapping("/hello")
   public void main(){ // 2. URL과 main()을 연결
       System.out.println("Hello");
   }
}

// ex) http://111.222.333.444:8080/ch2/hello 로 접속하면 main 메소드가 실행됨.
//                                 ch2 : Context root = project root

### URL로 원격 프로그램 실행시 메서드에 static이 없어도 실행되는 이유(static,private도 실행가능)
- 인스턴스 메서드는 객체생성 후 호출가능한데, 호출할 때 중간에서 누군가 tomcat 내부에서 객체생성을 해줘서 메서드 호출이 가능
```

### 로컬에서 개발한 소스를 원격tomcat으로 연결해서 실행하기

- export > war파일로 내보내기 (war = zip 똑같은 압축파일)
