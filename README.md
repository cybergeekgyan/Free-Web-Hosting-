# Free-Web-Hosting-
# Free Hosting on GitHub

This guide will take you from zero webserver knowledge, to having your own free site hosted on GitHub. The only non-free bit is registering a domain name, which can be as cheap as $5/year.

This guide uses CrazyDomains as the Registrar, FreeDNS as the DNS, and GitHub as the Webserver.

---

# 1) Domain Registration and Setup

The Domain Name Registrar is where you register your domain name, This is the only not free step.
Your registrar needs to know which DNS Server will associate the Domain Name with a WebServer.
I've got mine with [CrazyDomains](http://crazydomains.com.au), as they offer the cheapest `.com.au` domains.

1. Create an account, chuck in your payment details, etc.
1. Register your domain(s)
2. Set your domains `Name Servers` to `ns1.afraid.org`, ns2, ns3, and ns4.

---

# 2) Setup your DNS

Edit: Ignore this section and use CloudFlare instead. It's free, it's a DNS, It's _also_ a CDN, and it's _also_ easier.

I use [FreeDNS](http://freedns.afraid.org/), cause it's free, and doesn't look too dodgy.

1. Set up an account, login
2. Go to `Domains` -> `Add a Domain to FreeDNS`
  `Domain`: __yourdomain.com__
  `Shared State`: `Shared: Public`
2. Go to `Domains` -> __yourdomain.com__ -> `Manage`
3. Click the `Add` button at the top-right
  `Type`: `A`
  `Subdomain`: __blank__
  `Domain`: __yourdomain.com (public)(broken!)__
  `Destination`: `192.30.252.153`
  `Wildcard`: __ticked__
4. Click the `Add` button next to __yourdomain.com__ again, same settings as last time, but this time use the ip: `192.30.252.154`

---

# 3) Set Up your Website on GitHub

1. go to [GitHub.com](http://github.com), create an account, and login
2. Create a new Repository, mame it __yourdomain.com__, leave it as `Public`, and tick `Initialize this repository with a README``
3. Click `Settings` (in the right-middle -- for the repo, not for your account)
4. Under `Github Pages` click `Automatic page generator`
5. Make any changes you like, put in a Google Analytics ID if you want awesome free stats, click `Continue to layouts`
6. Choose a theme, or just go with the default and change it later. Click `Publish Page`
7. Your page can now be viewed at `http://<your github username>.github.io/<your repo name>/`
8. Back on your repo's page, click `Branch: master` and change to the `gh-pages` branch
9. Next to the Branch selector, it will show __yourdomain.com__, followed by a `/` and a `+`. Click the `+` to create a new file.
10. Name the file `CNAME` and put __yourdomain.com__ inside as the contents, click `Commit new file` to save it.


--

That's it! Everything's set up!

It can take up to 24 hours for the Domain Name to propogate, sometimes it only takes a few minutes thoughu. Until then browsing to __yourdomain.com__ will just return an error. If you're really impatient you can add it to your computer's __hosts__ file, otherwise just wait it out.


---

## Tips

- Settings -> Default branch: `gh-pages`
