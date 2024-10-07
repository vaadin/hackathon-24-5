# hackathon-24-5
Repository for the 24.5 hackathon

I only managed to deploy the Control-Center and a Test Application with security enabled for it.
I used the 200$ free credit (for 2 months) by DigitalOcean upon new SignUp, and the experience
was smooth. 

You can see the application deployed on the cloud K8s cluster:

1. Since I didn't have public domain and DNS setup at hand, I just added the following entry in
my local `/etc/hosts`:
```
209.38.182.250  app.firstproject
```
(Having the above entry in your `/etc/hosts` and bypass the securtiy warning in the browser you
should be able to browse the app.)

2. By browsing the https://app.firstproject you can see the application's public hello world page.
3. By signing in as user (`john.smith@example.com` and `johnsmith`) you can see the extra CRUD view. 
4. By signing in as admin (`jane.doe@example.com` and `janedoe`) you can see the dashboard view, too.

Followings were my findings:

## Reported Issues:
1. https://github.com/vaadin/control-center/issues/633
2. https://github.com/vaadin/control-center/issues/638
3. https://github.com/vaadin/control-center/issues/639
4. https://github.com/vaadin/control-center/issues/640
5. 
