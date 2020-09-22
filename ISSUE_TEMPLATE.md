Make sure you have provided the following information:

 - [X] link to your code branch cloned from rhboot/shim-review in the form user/repo@tag
 [Toolhouse-DV-Systeme/shim-review@toolhouse-shim-x64-20200922](https://github.com/Toolhouse-DV-Systeme/shim-review/tree/toolhouse-shim-x64-20200922)
 - [X] completed README.md file with the necessary information
 https://github.com/Toolhouse-DV-Systeme/shim-review/blob/toolhouse-shim-x64-20200922/README.md
 - [X] shim.efi to be signed
 https://github.com/Toolhouse-DV-Systeme/shim-review/blob/toolhouse-shim-x64-20200922/shim_toolhouse_x64.efi
 - [X] public portion of your certificate embedded in shim (the file passed to VENDOR_CERT_FILE)
 https://github.com/Toolhouse-DV-Systeme/shim-review/blob/toolhouse-shim-x64-20200922/Toolhouse.DER.cer
 - [ ] binaries, for which hashes are added do vendor_db ( if you use vendor_db and have hashes whitelisted )
 Not used
 - [X] any extra patches to shim via your own git tree or as files
 https://github.com/Toolhouse-DV-Systeme/shim/tree/toolhouse-15.1
 - [X] any extra patches to grub via your own git tree or as files
 https://github.com/Toolhouse-DV-Systeme/grub2/tree/grub_toolhouse_2_04_2
 - [X] build logs
 https://github.com/Toolhouse-DV-Systeme/shim-review/blob/toolhouse-shim-x64-20200922/build.log


###### What organization or people are asking to have this signed:
Toolhouse GmbH & Co. KG

https://www.toolhouse.de

###### What product or service is this for:

One of our most important products is TestLX, which is a hardware testing software which must be booted standalone on computers to be tested, examined or checked for bugs/errors.To enable TestLX for standalone use, it is based on a Debian Live Linux System, which is updated about quarterly.

###### What is the origin and full version number of your shim?

Shim is based on 'shim-15.1' from rhboot/shim
https://github.com/rhboot/shim/tree/shim-15.1

The tree with patches can be found at
https://github.com/Toolhouse-DV-Systeme/shim/tree/toolhouse-15.1

###### What's the justification that this really does need to be signed for the whole world to be able to boot it:

Since our product is used worldwide and at least several thousand times per day, it is essential that our users continue to be able to use SecureBoot worldwide without having to disable SecureBoot. Especially in the final product testing of computer manufacturers, it is required to not change any settings in the firmware setup. The same goes for computers in special environments like industry, healthcare, corporate environments.

We included SecureBoot support into TestLX six years ago. Back then, we had a Shim, which contained our public key, successfully signed by Microsoft. Since we had to renew the EV CodeSigning certificate, we now require the Shim to be signed with the new public key. We also used this occasion to update our Shim to the current version.

###### How do you manage and protect the keys used in your SHIM?

Keys are stored in a hardware token. Access to the token is restricted.

###### Do you use EV certificates as embedded certificates in the SHIM?

Yes, EV certificate issued by DigiCert.

###### If you use new vendor_db functionality, are any hashes whitelisted, and if yes: for what binaries ?

Not used, no binaries whitelisted

###### Is kernel upstream commit 75b0cea7bf307f362057cc778efe89af4c615354 present in your kernel, if you boot chain includes a linux kernel ?

Yes, kernel for release will be based on latest kernel from Ubuntu Focal Fossa.
Currently that is linux_5.4.0-48.52

75b0cea7bf307f362057cc778efe89af4c615354: since Ubuntu Linux_5_4_0-40.44

###### if SHIM is loading grub2 bootloader, is CVE CVE-2020-10713 fixed ?

Yes

Grub is branched from GRUB upstream commit e7b8856f8be3292afdb38d2e8c70ad8d62a61e10:
'linux: Fix integer overflows in initrd size handling'

##### Did you change your certificate strategy, so that affected by CVE CVE-2020-10713 grub2 bootloaders can not be verified ?

New shim uses new certificate.
No affected versions were signed with the new certificate.

###### What is the origin and full version number of your bootloader (GRUB or other)?

Bootloader based on GRUB 2.04+e7b8856f8be3292afdb38d2e8c70ad8d62a61e10
That commit is currently the upstream HEAD and includes the BootHole patches

The GRUB tree is avaiable from
https://github.com/Toolhouse-DV-Systeme/grub2/tree/toolhouse_2_04_2

###### If your SHIM launches any other components, please provide further details on what is launched

Shim is only used to launch a GRUB 2.04 based bootloader.

###### How do the launched components prevent execution of unauthenticated code?

Loaded code is validated through shim.
Linux is validated through linuxefi from fedora-33 branch of rhboot.
No other code is loaded.

###### Does your SHIM load any loaders that support loading unsigned kernels (e.g. GRUB)?

No, our GRUB flavor does not load any unsigned kernels when SecureBoot mode is active
We use a modified GRUB 2.04 with shim_lock verifier.

###### What kernel are you using? Which patches does it includes to enforce Secure Boot?

Latest Linux kernel from Ubuntu with modified configuration
We update the kernel version quaterly.
Secureboot-Lockdown options are kept enabled in the configuration.

###### What changes were made since your SHIM was last signed?

Update from shim '12' to 'shim-15.1'
Renewed certificate
Added 'Check PxeReplyReceived as fallback in netboot' patch 
Enabled HTTPBoot option

###### What is the hash of your final SHIM binary?
Sha256 hash: 0bce3e7af4aa1658025ef88a6c2d9e615c250d3f41fe6f3b1bfc28cfc5431af1
