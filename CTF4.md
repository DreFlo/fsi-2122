We accessed the website and took the time to browse through it, noting the two users (Admin & Orval Sanford), and seeing the information on the product description and the additional information for the Wordpress Hosting.
From it we got the program version for Wordpress, WooCommerce plugin & Booster for WooCommerce Pluggin.
We researched different CVE's for each of the program's versions, ending up with find one for the Booster for WooCommerce Pluggin (CVE-2021-34646) which allowed bypassing the authentication feature.
We found an exploit (EBD-ID: 50299) which required us to select an user ID (we used Admin, as we knew existed, with the number 1 as is common), which triggered an e-mail verification and, then, successfully logged in as the user in question (in this case the Admin).
In doing so, we access the website link provided, in which we found a message about website security and, in it, we found the flag to submit (flag{d8e2c772b2f4f972782d3d52805eb82d}).
