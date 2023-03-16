# jenkins-issue
Jenkins < 2.266 has trustbound problem(CWE-501).
when use username/password as admin/admin and login successful,it will happen.
```
"trustBound": [
            {
                "headers": {
                    "Cookie": "screenResolution=2552x1217; JSESSIONID.241be1ea=node02chzhvb894ii3xkr9qq4npsf7.node0",
                    "Origin": "http://127.0.0.1:8080"
                },
                "params": {
                    "j_password": "admin",
                    "Submit": "Sign in",
                    "from": "/",
                    "j_username": "admin"
                },
                "url": "http://192.168.199.130:8080/j_acegi_security_check",
                "method": "POST",
                "problemType": "trustBound",
                "problemData": "org.eclipse.jetty.server.session.Session.setAttribute(Session.java) 
                hudson.security.AuthenticationProcessingFilter2.determineTargetUrl(AuthenticationProcessingFilter2.java:54)
                org.acegisecurity.ui.AbstractProcessingFilter.successfulAuthentication(AbstractProcessingFilter.java:480) 
                org.acegisecurity.ui.AbstractProcessingFilter.doFilter(AbstractProcessingFilter.java:266) 
                hudson.security.ChainedServletFilter$1.doFilter$original$FS5SWfCg(ChainedServletFilter.java:87) 
                hudson.security.ChainedServletFilter$1.doFilter$original$FS5SWfCg$accessor$1Yt3KUlh(ChainedServletFilter.java) 
                hudson.security.ChainedServletFilter$1$auxiliary$IXL5Ydmf.call(Unknown Source) 
                hudson.security.ChainedServletFilter$1.doFilter(ChainedServletFilter.java) 
                jenkins.security.BasicHeaderProcessor.doFilter(BasicHeaderProcessor.java:93) 
                hudson.security.ChainedServletFilter$1.doFilter$original$FS5SWfCg(ChainedServletFilter.java:87) 
                hudson.security.ChainedServletFilter$1.doFilter$original$FS5SWfCg$accessor$1Yt3KUlh(ChainedServletFilter.java) 
                hudson.security.ChainedServletFilter$1$auxiliary$IXL5Ydmf.call(Unknown Source) 
                hudson.security.ChainedServletFilter$1.doFilter(ChainedServletFilter.java) 
                org.acegisecurity.context.HttpSessionContextIntegrationFilter.doFilter(HttpSessionContextIntegrationFilter.java:249) 
                hudson.security.HttpSessionContextIntegrationFilter2.doFilter(HttpSessionContextIntegrationFilter2.java:67) 
                hudson.security.ChainedServletFilter$1.doFilter$original$FS5SWfCg(ChainedServletFilter.java:87) 
                hudson.security.ChainedServletFilter$1.doFilter$original$FS5SWfCg$accessor$1Yt3KUlh(ChainedServletFilter.java) 
                hudson.security.ChainedServletFilter$1$auxiliary$IXL5Ydmf.call(Unknown Source) 
                hudson.security.ChainedServletFilter$1.doFilter(ChainedServletFilter.java) 
                hudson.security.ChainedServletFilter.doFilter(ChainedServletFilter.java:90)
                hudson.security.HudsonFilter.doFilter(HudsonFilter.java:171) org.eclipse.jetty.servlet.FilterHolder.doFilter(FilterHolder.java:193) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter$original$bwotlJIw(ServletHandler.java:1609) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter$original$bwotlJIw$accessor$C7AUDKxT(ServletHandler.java) 
                org.eclipse.jetty.servlet.ServletHandler$Chain$auxiliary$vvv1Z5CN.call(Unknown Source) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter(ServletHandler.java) 
                org.kohsuke.stapler.compression.CompressionFilter.doFilter(CompressionFilter.java:51) 
                org.eclipse.jetty.servlet.FilterHolder.doFilter(FilterHolder.java:193) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter$original$bwotlJIw(ServletHandler.java:1609) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter$original$bwotlJIw$accessor$C7AUDKxT(ServletHandler.java) 
                org.eclipse.jetty.servlet.ServletHandler$Chain$auxiliary$vvv1Z5CN.call(Unknown Source) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter(ServletHandler.java) 
                hudson.util.CharacterEncodingFilter.doFilter(CharacterEncodingFilter.java:82) 
                org.eclipse.jetty.servlet.FilterHolder.doFilter(FilterHolder.java:193) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter$original$bwotlJIw(ServletHandler.java:1609) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter$original$bwotlJIw$accessor$C7AUDKxT(ServletHandler.java) 
                org.eclipse.jetty.servlet.ServletHandler$Chain$auxiliary$vvv1Z5CN.call(Unknown Source) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter(ServletHandler.java) 
                org.kohsuke.stapler.DiagnosticThreadNameFilter.doFilter(DiagnosticThreadNameFilter.java:30) 
                org.eclipse.jetty.servlet.FilterHolder.doFilter(FilterHolder.java:193) 
                org.eclipse.jetty.servlet.ServletHandler$Chain.doFilter$original$bwotlJIw(ServletHandler.java:1609) ",
                "time": "2023-03-16 16:06:55"
            }
        ]
```
