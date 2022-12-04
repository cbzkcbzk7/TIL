## HttpServletRequest

- 브라우저에서 URL로 요청을 하면 Tomcat이 HttpServletRequest 객체를 만들어서 요청한 정보를 담고, 메서드의 매개변수에 넣어줌

```java
// HttpServletRequest

@Controller
public class RequestInfo {
    public void main(HttpServletRequest request){ // tomcat에서 넣어줌

        System.out.println("request.getMethod() ="+request.getMethod()); // request 객체를 이용해 요청 정보를 받을 수 있음
        System.out.println("request.getProtocol() ="+request.getProtocol());
        System.out.println("request.getScheme() ="+request.getScheme());
    }
}

```

### HttpServletRequest의 메서드

                                --8.getRequestURI()--
            2.getServerName()   4.getContextPath() 6.getQueryString()

#### ex) http://52.78.79.190:8080/ch2/requestInfo?year=2021&month=10&day=1

        1.getScheme()   3.getServerPort() 5.getServletPath()
     --------- 7.getRequestURL() ---------------

### HttpServletRequest / HttpServletResponse 로 출력하기

```java
@Controller
public class YoilTeller {

	@RequestMapping("/getYoil")
    public void main(HttpServletRequest request, HttpServletResponse response) throws IOException {
    	// 1.입력
    	String year = request.getParameter("year");
    	String month = request.getParameter("month");
    	String day = request.getParameter("day");

    	int yyyy = Integer.parseInt(year);
    	int mm = Integer.parseInt(month);
    	int dd = Integer.parseInt(day);

    	//2. 작업
    	Calendar cal = Calendar.getInstance();
    	cal.set(yyyy, mm-1, dd);

    	int dayOfWeek = cal.get(Calendar.DAY_OF_WEEK); // 1:일, 2: 월 ...
    	char yoil = " 일월화수목금토".charAt(dayOfWeek);

    	//3. 출력
    	response.setContentType("text/html"); //  출력할 형식 써줘야함 : 브라우저는 내가 보내는 내용이 텍스트인지 바이너리인지 모름
    	response.setCharacterEncoding("utf-8"); // 텍스트의 인코딩을 알려줌
    	PrintWriter out = response.getWriter(); // response객체에서 브라우저로의 출력 스트림을 얻는다.
    	out.println(year + "년 "+ month +"월 "+ day + "일은 ");
    	out.println(yoil +"요일입니다.");
    }
}
```

## 리소스(서버가 제공하는 리소스)

1. 동적리소스 : 프로그램, 스트리밍
2. 정적리소스 : _.js, _.css, \*.html
