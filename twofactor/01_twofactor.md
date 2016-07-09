!SLIDE incremental
# Two- (or Multi-) Factor Auth
* Not new! We're just using it differently now.
* Something you know: password, PIN
* Something you have: crypto token, smartcard, phone, ATM card
* Something you are: biometrics
* Usually use "know" and "have" because "are" is expensive and difficult

~~~SECTION:notes~~~

Hidden lock: had to know where the lock was, and have the key. Safe that
required a key and a combination.

Many biometrics have been found to be unreliable - fake fingers, etc. They're
becoming cheap and still unreliable.

~~~ENDSECTION~~~

!SLIDE
# GitHub Two-Factor Auth
* Web UI only, does not prompt every time
* SMS
* TOTP (Google Authenticator, Authy)
* FIDO U2F
* Backup codes
* Personal Access Tokens

~~~SECTION:notes~~~

Does not affect SSH keys for git-over-ssh, just your ability to add/remove your
keys.

~~~ENDSECTION~~~

!SLIDES
# GitHub Two-Factor Auth
## SMS
* Sends a numeric code for you to enter after your password
* Most cell phones from the past couple of decades
* Requires cell reception
* Probably won't work with all carriers worldwide
* People have hijacked cell phone numbers with fake IDs, etc.

~~~SECTION:notes~~~

Technically this might be more accurately called out-of-band verification.

~~~ENDSECTION~~~

!SLIDES
# GitHub Two-Factor Auth
## TOTP
* Time-based One Time Password, [RFC 6238](https://tools.ietf.org/html/rfc6238)
* Generated single-use numeric codes
* Smartphone: Google Authenticator, Authy, etc.
* Scan the QR code or manually enter the key, then submit a code from the app
* Open-source implementations available in several languages

!SLIDES
# GitHub Two-Factor Auth
## FIDO Alliance U2F (aka Security Key)
* Fast IDentity Online, Universal 2nd Factor, <https://fidoalliance.org/>
* USB auth token, size/shape like a thumb drive
* Support built in to browser, currently only Chrome (Firefox has an extension)
* Plug it in, press the button, cryptographic challenge-response
* Only supported by tech companies: ie Google, GitHub, not your bank

~~~SECTION:notes~~~

Spec doesn't limit you to USB, but that's the available implementation. Also
supports capabilities that aren't available in current USB tokens.

Google and GitHub call it "security key", but PayPal's "security key" is
actually the Symantec authenticator app (used to be a physical token).

Firefox has an open Bugzilla enhancement ticket for it, but right now you have
to use an extension.

~~~ENDSECTION~~~

!SLIDES
# GitHub Two-Factor Auth
## Backup codes
* To be used when other mechanisms are not available
* A list of one-time-use static codes
* Print/save and keep somewhere safe

!SLIDES
# GitHub Two-Factor Auth
## Personal Access Tokens
* Needed when you can't be prompted for a secondary code
* Apps that integrate with GitHub
* API calls
* git-over-https

