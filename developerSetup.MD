# Developer Setup

To work on the software for this project, you'll need to install the free [PSoC® Creator™](http://www.cypress.com/products/psoc-creator-integrated-design-environment-ide) software that Cypress provides.  

NOTE:
 It makes me a little nervous that Cypress has decided to require installation of the Akamai Download Manager, which generates firewall warnings by default on Windows 10.   Furthermore the PSoC Creator software depends on the .NET Framwork version 3.5, which isn't installed by default on Windows 10 machine.   With that said, neither of these dependencies have a bad reputation as far as I'm concerned, so I've installed the prerequsites, and will briefly say that installing .NET 3.5 on Win 10 involved **Control Panel/Programs and Features/Turn Windows Features on or off**.  A client app like this should only require the basic .NET features, not the HTTP handler options.     