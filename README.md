# Free-Web-Hosting-
Free Hosting on GitHub
This guide will take you from zero webserver knowledge, to having your own free site hosted on GitHub. The only non-free bit is registering a domain name, which can be as cheap as $5/year.

This guide uses CrazyDomains as the Registrar, FreeDNS as the DNS, and GitHub as the Webserver.

1) Domain Registration and Setup
The Domain Name Registrar is where you register your domain name, This is the only not free step. Your registrar needs to know which DNS Server will associate the Domain Name with a WebServer. I've got mine with CrazyDomains, as they offer the cheapest .com.au domains.

Create an account, chuck in your payment details, etc.
Register your domain(s)
Set your domains Name Servers to ns1.afraid.org, ns2, ns3, and ns4.
2) Setup your DNS
Edit: Ignore this section and use CloudFlare instead. It's free, it's a DNS, It's also a CDN, and it's also easier.

I use FreeDNS, cause it's free, and doesn't look too dodgy.

Set up an account, login
Go to Domains -> Add a Domain to FreeDNS Domain: yourdomain.com Shared State: Shared: Public
Go to Domains -> yourdomain.com -> Manage
Click the Add button at the top-right Type: A Subdomain: blank Domain: yourdomain.com (public)(broken!) Destination: 192.30.252.153 Wildcard: ticked
Click the Add button next to yourdomain.com again, same settings as last time, but this time use the ip: 192.30.252.154
3) Set Up your Website on GitHub
go to GitHub.com, create an account, and login
Create a new Repository, mame it yourdomain.com, leave it as Public, and tick `Initialize this repository with a README``
Click Settings (in the right-middle -- for the repo, not for your account)
Under Github Pages click Automatic page generator
Make any changes you like, put in a Google Analytics ID if you want awesome free stats, click Continue to layouts
Choose a theme, or just go with the default and change it later. Click Publish Page
Your page can now be viewed at http://<your github username>.github.io/<your repo name>/
Back on your repo's page, click Branch: master and change to the gh-pages branch
Next to the Branch selector, it will show yourdomain.com, followed by a / and a +. Click the + to create a new file.
Name the file CNAME and put yourdomain.com inside as the contents, click Commit new file to save it.
--

That's it! Everything's set up!

It can take up to 24 hours for the Domain Name to propogate, sometimes it only takes a few minutes thoughu. Until then browsing to yourdomain.com will just return an error. If you're really impatient you can add it to your computer's hosts file, otherwise just wait it out.

Tips
Settings -> Default branch: gh-pages
