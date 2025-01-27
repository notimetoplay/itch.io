{
  title: "Secure your account with 2FA"
  share_message: "A guide on how to secure your itch.io account using two-factor authentication."
  amp: true
}

We take the security of your account and personal information seriously.
**itch.io** supports two-factor authentication via TOTP (Time-based One-time
Password Algorithm), in addition to simple password authentication.

<div class="button_row">
<a href="/developers" class="button fat on_logged_out">Create an account with itch.io</a>
<a href="/user/settings/two-factor-auth" class="button fat on_logged_in">Set up two-factor authentication</a>
<div class="sub">or read on to learn more</div>
</div>

## What is two-factor authentication?

The idea behind two-factor authentication is that, to increase
security, login should not only require something you know (like a password),
but also something you have (like a token).

The objective is to prevent third parties from gaining unauthorized
access to your account. One possible implementation is to send an SMS to
your mobile whenever you try to log in, after you've typed your password.

This way, an attacker would not only have to know your password, but also
be in possession of your mobile phone - or at least, find a way to receive
your text messages.

While no system is perfectly secure, this is a step towards ensuring
that you and only you can access your account.

## What is TOTP?

TOTP (Time-based One-Time Password algorithm) is a [standard algorithm][rfc6238]
that computes a one-time password from a share key and the current time.

It is one of the less constraining and most robust forms of two-factor authentication,
and is currently used by [companies][] such as GitHub, Amazon, and Facebook.

## How do I use TOTP?

Setting up TOTP is as easy as following the instructions in the **Security** tab
of your user settings.

The first step involves scanning a QR code on your mobile via one of the supported
TOTP mobile applications. We recommend using:

  - [Google Authenticator][gauth] on Android, iOS and Blackberry
  - [Authenticator][auth] for Windows Phone

The QR code contains the shared secret, as well as helpful reminders such
as your account name, and the issuer (in this case, itch.io).

Once TOTP has been enabled, logging into your account will require you
to enter a 6-digit code in addition to your password. The verification
code is automatically generated by the mobile app you've installed, and
changes every 30 seconds.

## My verification codes are getting refused. What's happening?

Since verification codes are time-dependent, any offset between your
phone's clock and the server time might result in a failed authentication.

In this case, we advise you to adjust your phone's clock to the correct
time. Most mobile operating systems provide a network-based way to automatically
adjust your phone to the right time.

## What happens if I lose access to my phone?

When enabling two-factor authentication, a set of 8-digit recovery codes
is generated. You should print them and keep them with you whenever you
might need to log in to the site.

These codes allow you to log in without using your mobile phone at all.
It is imperative for you to keep them in a safe place to avoid being locked
out of your account.

## Do you support SMS?

SMS two-factor authentication [has been deprecated by NIST experts][sms-2fa]
and will not be added to itch.io. TOTP two-factor authentication is a better
guarantee and works even without mobile network coverage.

[gauth]: https://support.google.com/accounts/answer/1066447?hl=en
[auth]: https://www.microsoft.com/en-us/store/apps/authenticator/9wzdncrfj3rj
[rfc6238]: http://tools.ietf.org/html/rfc6238
[companies]: http://en.wikipedia.org/wiki/Google_Authenticator#Usage
[sms-2fa]: https://techcrunch.com/2016/07/25/nist-declares-the-age-of-sms-based-2-factor-authentication-over/

