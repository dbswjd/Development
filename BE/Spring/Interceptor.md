# Interceptor
Controlle로 가느 호출을 가로채서 특정 처리를 하는 역할

## HandlerInterceptor Methods
### preHandle(request, response, handler)
지정된 컨트롤러의 동작 이전에 수행하 동작

### postHandle(request, response, handler, modelAndView)
지정된 컨트롤러의 동작 이후에 수행하 동작 
Spring MVC의 Dispatcher Servlet이 화면을 처리하기 전에 동작 

### afterCompletion(request, response, handler, exception)
Dispatcher Servlet의 화면 처리가 완료되 이후 처리할 동작 

## Interceptor 설정 

``` java
public class SampleInterceptor extends HandlerInterceptorAdaptor {
    
    @Override
    public boolean preHandler(HttpServletRequest request, HttpServletResponse response,Object handler) throws Exception {        
        System.out.println("pre handle........");
        return true;
    }

    @Override
    public void postHandler(HttpServletRequest request, HttpServletResponse response, Object handler, ModelAndView modelAndView) throws Exception {        
        System.out.println("post handle.......");
    }
}
```

## Interceptor Congifuration
``` Java
@Configuration
public class WebConfig implements WebMvcConfigurer {
  @Bean
  public SampleInterceptor sampleInterceptor() {
    SampleInterceptor sampleInterceptor = new SampleInterceptor();
    return sampleInterceptor;
  }

  @Override
  public void addInterceptors(InterceptorRegistry registry) {
    registry.addInterceptor(sampleInterceptor())
            .addPathPatterns("/**")
	          .excludePathPatterns("/swagger-ui.html")
	    }
}

```


