# Set up OpenVPN

add what is required before user can use portal

This is a guide to set up SHIP-HATS [OpenVPN](https://vpn.ship.gov.sg) on Internet devices. All users are required to set up OpenVPN when onboarding to SHIP-HATS or when a reset is needed due to a version upgrade or other reasons. Users connect to OpenVPN to log in to SHIP-HATS Portal and SHIP-HATS tools such as Jira, Confluence, Bitbucket, Bamboo, Sonarqube, and Nexus.

SHIP-HATS enforces two-factor authentication for OpenVPN to provide an additional layer of security.

### To set up OpenVPN:

1. Go to [SHIP-HATS OpenVPN](https://vpn.ship.gov.sg/) in your internet facing PC or Mac.
Note: This website is not supported by Safari.
1. Enter the **username** provided in the onboarding email from the SHIP-HATS administrator.
1. Enter **password** you have set using the link provided in onboarding email.
1. Click **Sign In**.

    ![open vpn](openvpn11.png  ':size=60%')

1. Install and open **Authy** or **Google Authenticator** on your mobile phone from App store or Google Play Store.
1. Tap + and choose **Scan a QR code**.
1. Scan the QR code displayed on your internet device. Your OpenVPN account gets added and a six-digit code is displayed on your mobile phone.
1. Enter this six-digit code without any space and click **Confirm Code**.
1. Download and install the client applicable for your OS(operating system) from the highlighted group as shown in Box 1 in Figure 1
1. Click **Yourself (user-locked profile)** to download your personal connection profile (.ovpn file) as shown in Box 2 in Figure 1

    ![figure 1](openvpnchoose.png  ':size=60%')

1. Open OpenVPN and import the downloaded profile by clicking **+**. 

    ![openvpn](openvpn1up.png  ':size=60%')

1. Go to **File** and click **Browse** to locate the downloaded .ovpn file and click **Add**.
1. Enter your SHIP-HATS log in credentials on the Imported profile page as shown in figure 1.2 and click connect.

    ![figure 1-3](openvpn22.png  ':size=60%')

1. You have successfully installed OpenVPN. You will need to log in to OpenVPN each time you require access to SHIP-HATS.

    >**Note:** You need to reset the 2FA if you uninstall the Authy/Authenticator app or when you change the phone instrument.

### FAQs
- **Is there any IP or regional restriction for incoming VPN connections?**
    
    There are no IP restrictions on incoming connectivity.
- **Are there any device requirements?** 
    
    No, any internet device works.
- **How do I set up OpenVPN?** 
    
    You will receive an email from your SHIP-HATS administrator containing your username and password details. Go to <a href="https://vpn.ship.gov.sg/">OpenVPN</a> and log in with your SHIP-HATS credentials.
- **Which operating systems are supported by OpenVPN?**

    OpenVPN works on Linux, Mac, Windows, Android and iOS.