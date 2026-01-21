Used to reproduce some Jenkins bug in isolated environment

## Steps to reproduce

Run the job and replay it.

```
Caught unhandled exception with ID 5b39cbb2-bba3-4d2a-bb41-d390b9928ee4
java.lang.IllegalStateException: Form is larger than max length 200000
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.nested.Request.extractFormParameters(Request.java:560)
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.nested.Request.extractContentParameters(Request.java:518)
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.nested.Request.getParameters(Request.java:378)
Caused: org.eclipse.jetty.http.BadMessageException: 400: Unable to parse form content
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.nested.Request.getParameters(Request.java:383)
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.nested.Request.getParameterNames(Request.java:1044)
	at Jenkins Main ClassLoader//jakarta.servlet.ServletRequestWrapper.getParameterNames(ServletRequestWrapper.java:166)
	at hudson.security.csrf.CrumbFilter.extractCrumbFromRequest(CrumbFilter.java:167)
	at hudson.security.csrf.CrumbFilter.doFilter(CrumbFilter.java:136)
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.servlet.FilterHolder.doFilter(FilterHolder.java:202)
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.servlet.ServletHandler$Chain.doFilter(ServletHandler.java:1637)
	at jenkins.security.csp.impl.CspFilter.doFilter(CspFilter.java:79)
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.servlet.FilterHolder.doFilter(FilterHolder.java:202)
	at Jenkins Main ClassLoader//org.eclipse.jetty.ee9.servlet.ServletHandler$Chain.doFilter(ServletHandler.java:1637)
	at hudson.security.ChainedServletFilter2$1.doFilter(ChainedServletFilter2.java:94)
	at PluginClassLoader for oic-auth//org.jenkinsci.plugins.oic.OicSecurityRealm$1.doFilter(OicSecurityRealm.java:740)
	at hudson.security.ChainedServletFilter2$1.doFilter(ChainedServletFilter2.java:99)
	at hudson.security.ChainedServletFilter2$1.doFilter(ChainedServletFilter2.java:94)
```

That's all folks!

> [!NOTE]
> DOn't use such configuration in production. It's unsecure
