# Create a learning site based on Open edX
## Related documents
Notes when installing and configuring: link
Homepage design: link
## Installing and Configuring
### Resources needed to deploy
- A domain
- A DigitalOcean droplet or a server (self-hosted, cloud providers)	
- A Paypal and a Cybersource account

### Site installation & configuration
#### Versions
- Tutor: 16.0.2
- Open edX: Palm (open-release/palm.1)

#### Install Tutor
[Tutor full documentation](https://docs.tutor.overhang.io/index.html)

Need config the following sub-domains:
- preview.*
- apps.*
- ecommerce.*

Build image
```bash
tutor images build openedx --build-arg EDX_PLATFORM_REPOSITORY=https://github.com/vinhdoanthe/edx-platform.git --build-arg EDX_PLATFORM_VERSION=feature/palm-1-uw-project-01
```

Create a superuser account: #TODO
## Update homepage content
Go to **YOUR_LMS_DOMAIN**/cms/
Log in with a superuser account

## Create a course and update course content
Go to **YOUR_CMS_DOMAIN**
Log in with a staff/superuser account

## Create a course on e-commerce service
Go to **YOUR_ECOMMERCE_DOMAIN**/courses/
Log in with the superuser account created at …
## Notes
If the payment page gets the 404 error, we need to rebuild the mfe plugin
tutor images build mfe
## Important references
- Documentation for technical operators: https://edx.readthedocs.io/projects/edx-installing-configuring-and-running/en/latest/index.html
- Documentation for educators: https://docs.openedx.org/en/latest/educators/how-tos/index.html 
- Documentation for learners: https://edx.readthedocs.io/projects/open-edx-learner-guide/en/latest/ 
- Create products on e-commerce: https://edx-ecommerce.readthedocs.io/en/latest/create_products/create_course_seats.html 
