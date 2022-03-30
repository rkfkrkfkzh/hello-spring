# hello-spring
java.lang.IllegalStateException: Failed to load ApplicationContext

memoryMemberRepository클래스의 어노테이션 @Repository 주석 처리하니 정상 컴파일
@Bean에서 이미 Repository 의존성 주입을 해서 @Repository를 무시한것 같음.
그래서 Repository용 @Bean이 전부 주석 처리 되었을 때 memberRepository를 spring이 알아서 가져오는데 memoryMemberRepository클래스의 어노테이션 @Repository를 안지워주면 인터페이스 JpaRepository와 같이 처리되는 듯함...
SpringDataJpaMemberRepository는 스프링이 자동으로 스프링 빈으로 등록해준다. 코드를 보면 MemberRepository를 Bean으로 등록한 부분이 없다 대신 MemberRepository를 스프링으로 부터 주입 받아 사용하는 부분이 있다.