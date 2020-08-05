Make sure you have provided the following information:

 - [X] link to your code branch cloned from rhboot/shim-review in the form user/repo@tag
 https://github.com/Toolhouse-DV-Systeme/shim-review/tree/toolhouse-shim-x64-20200728
 - [X] completed README.md file with the necessary information
 https://github.com/Toolhouse-DV-Systeme/shim-review/blob/toolhouse-shim-x64-20200728/README.md
 - [X] shim.efi to be signed
 https://github.com/Toolhouse-DV-Systeme/shim-review/blob/toolhouse-shim-x64-20200728/shim_toolhouse_x64.efi
 - [X] public portion of your certificate embedded in shim (the file passed to VENDOR_CERT_FILE)
 https://github.com/Toolhouse-DV-Systeme/shim-review/blob/toolhouse-shim-x64-20200728/Toolhouse.DER.cer
 - [X] any extra patches to shim via your own git tree or as files
 https://github.com/Toolhouse-DV-Systeme/shim/tree/toolhouse-15_2
 - [X] any extra patches to grub via your own git tree or as files
 https://github.com/Toolhouse-DV-Systeme/grub2/tree/grub_toolhouse_2_04_2
 - [X] build logs
 https://github.com/Toolhouse-DV-Systeme/shim-review/blob/toolhouse-shim-x64-20200728/build.log


###### What organization or people are asking to have this signed:
Toolhouse GmbH & Co. KG

https://www.toolhouse.de

###### What product or service is this for:

One of our most important products is TestLX, which is a hardware testing software which must be booted standalone on computers to be tested, examined or checked for bugs/errors.To enable TestLX for standalone use, it is based on a Debian Live Linux System, which is updated about quarterly.

###### What is the origin and full version number of your shim?

Shim is based on shim 15 from rhboot/shim
https://github.com/Toolhouse-DV-Systeme/shim/tree/toolhouse-15_2

###### What's the justification that this really does need to be signed for the whole world to be able to boot it:

Since our product is used worldwide and at least several thousand times per day, it is essential that our users continue to be able to use SecureBoot worldwide without having to disable SecureBoot. Especially in the final product testing of computer manufacturers, it is required to not change any settings in the firmware setup. The same goes for computers in special environments like industry, healthcare, corporate environments.

We included SecureBoot support into TestLX six years ago. Back then, we had a Shim, which contained our public key, successfully signed by Microsoft. Since we had to renew the EV CodeSigning certificate, we now require the Shim to be signed with the new public key. We also used this occasion to update our Shim to the current version.

###### How do you manage and protect the keys used in your SHIM?

Keys are stored in a hardware token. Access to the token is restricted.

###### Do you use EV certificates as embedded certificates in the SHIM?

Yes, EV certificate issued by DigiCert.

###### What is the origin and full version number of your bootloader (GRUB or other)?

Bootloader based on GRUB 2.04+e7b8856f8be3292afdb38d2e8c70ad8d62a61e10
That commit is currently the upstream HEAD and includes the BootHole patches

The GRUB tree is avaiable from
https://github.com/Toolhouse-DV-Systeme/grub2/tree/toolhouse_2_04_2

###### If your SHIM launches any other components, please provide further details on what is launched

Shim is only used to launch a GRUB 2.04 based bootloader.

###### How do the launched components prevent execution of unauthenticated code?

GRUB 2.04 uses shim_lock verification to validate loaded kernels
BootHole patches are applied

###### Does your SHIM load any loaders that support loading unsigned kernels (e.g. GRUB)?

No, our GRUB flavor does not load any unsigned kernels when SecureBoot mode is active
We use a modified GRUB 2.04 with shim_lock verifier.

###### What kernel are you using? Which patches does it includes to enforce Secure Boot?

Latest Linux kernel from Ubuntu with modified configuration
We update the kernel version quaterly.
Secureboot-Lockdown options are kept enabled in the configuration.

###### What changes were made since your SHIM was last signed?

Update from shim 12 to shim 15
Renewed certificate
Added 'Check PxeReplyReceived as fallback in netboot' patch 
Enabled HTTPBoot option

###### What is the hash of your final SHIM binary?
Sha256 hash: 132e782a22beb0cfae833b7fc946e0910725b7848585e9e507157d8c9139ad29
