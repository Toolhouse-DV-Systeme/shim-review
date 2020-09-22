This repo is for review of requests for signing shim.  To create a request for review:

- clone this repo
- edit the template below
- add the shim.efi to be signed
- add build logs
- add any additional binaries/certificates/hashes that may be needed
- commit all of that
- tag it with a tag of the form "myorg-shim-arch-YYYYMMDD"
- push that to github
- file an issue at https://github.com/rhboot/shim-review/issues with a link to your branch
- approval is ready when you have accepted tag

Note that we really only have experience with using grub2 on Linux, so asking
us to endorse anything else for signing is going to require some convincing on
your part.

Here's the template:

-------------------------------------------------------------------------------
What organization or people are asking to have this signed:
-------------------------------------------------------------------------------
Toolhouse GmbH & Co. KG

Our main focus is to provide solutions to test hardware, mainly PC-based
computers, notebooks, tablets and other devices. Toolhouse products are used 
worldwide, especially by (but not limited to) computer manufacturers, computer
service and repair companies and IT service providers.


-------------------------------------------------------------------------------
What product or service is this for:
-------------------------------------------------------------------------------
One of our most important products is TestLX, which is a hardware testing
software which must be booted standalone on computers to be tested, examined or
checked for bugs/errors.To enable TestLX for standalone use, it is based on a
Debian Live Linux System, which is updated about quarterly.


-------------------------------------------------------------------------------
What's the justification that this really does need to be signed for the whole world to be able to boot it:
-------------------------------------------------------------------------------
Since our product is used worldwide and at least several thousand times per day,
it is essential that our users continue to be able to use SecureBoot worldwide
without having to disable SecureBoot. Especially in the final product testing
of computer manufacturers, it is required to not change any settings in the
firmware setup. The same goes for computers in special environments like
industry, healthcare, corporate environments.

We included SecureBoot support into TestLX six years ago. Back then, we had a
Shim, which contained our public key, successfully signed by Microsoft.
We update our Shim to the current release. 


-------------------------------------------------------------------------------
Who is the primary contact for security updates, etc.
-------------------------------------------------------------------------------
- Name: Denkhaus, Volker
- Position:
- Email address: <denkhaus@toolhouse.de>

Denkhaus, Volker   -ToolHouse- <denkhaus@toolhouse.de>
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: GnuPG v2

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
dmk=
=I6/B
-----END PGP PUBLIC KEY BLOCK-----

-------------------------------------------------------------------------------
Who is the secondary contact for security updates, etc.
-------------------------------------------------------------------------------
- Name: Leinzinger, Ludwig
- Position:
- Email address: <leinzinger@toolhouse.de>

Leinzinger, Ludwig   -ToolHouse- <leinzinger@toolhouse.de>
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: GnuPG v2

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
kaiJQdfR
=8c17
-----END PGP PUBLIC KEY BLOCK-----



Michael Haunreiter | Miray Software <mh@miray.de>
-----BEGIN PGP PUBLIC KEY BLOCK-----
Version: GnuPG v2

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
3ROZo6Q2uT+t
=ZQ2f
-----END PGP PUBLIC KEY BLOCK-----


-------------------------------------------------------------------------------
What upstream shim tag is this starting from:
-------------------------------------------------------------------------------

https://github.com/rhboot/shim/tree/shim-15.1

-------------------------------------------------------------------------------
URL for a repo that contains the exact code which was built to get this binary:
-------------------------------------------------------------------------------
https://github.com/Toolhouse-DV-Systeme/shim/tree/toolhouse-15.1

-------------------------------------------------------------------------------
What patches are being applied and why:
-------------------------------------------------------------------------------
* Fix build error in mok.c
    This fixes a build error in mok.c.
    
* Check PxeReplyReceived as fallback in netboot
   This adds a fallback to check the PxeReply field if no boot information is
   found in the v4 dhcp or proxy dhcp information
   This can be necessary when a boot menu is used 
   (Patch was accepted upstream)

-------------------------------------------------------------------------------
If bootloader, shim loading is, grub2: is CVE-2020-10713 fixed ?
-------------------------------------------------------------------------------
Yes

Grub is branched from GRUB upstream commit e7b8856f8be3292afdb38d2e8c70ad8d62a61e10:
'linux: Fix integer overflows in initrd size handling'

-------------------------------------------------------------------------------
If bootloader, shim loading is, grub2, and previous shims were trusting affected
by CVE-2020-10713 grub2:
* were old shims hashes provided to Microsoft for verification
  and to be added to future DBX update ?
* Does your new chain of trust disallow booting old, affected by CVE-2020-10713,
  grub2 builds ?
-------------------------------------------------------------------------------
* were old shims hashes provided to Microsoft for verification
  and to be added to future DBX update:
  
Hashes will be provided after new SHIM has been signed.


* Does your new chain of trust disallow booting old, affected by CVE-2020-10713,
  grub2 builds:

New shim uses new certificate.
No affected versions were signed with the new certificate. 

-------------------------------------------------------------------------------
If your boot chain of trust includes linux kernel, is
"efi: Restrict efivar_ssdt_load when the kernel is locked down"
upstream commit 1957a85b0032a81e6482ca4aab883643b8dae06e applied ?
Is "ACPI: configfs: Disallow loading ACPI tables when locked down"
upstream commit 75b0cea7bf307f362057cc778efe89af4c615354 applied ?
-------------------------------------------------------------------------------

Yes, kernel for release will be based on latest kernel from Ubuntu Focal Fossa.
Currently that is linux_5.4.0-48.52

1957a85b0032a81e6482ca4aab883643b8dae06e: since linux_5.4.0-43.47
75b0cea7bf307f362057cc778efe89af4c615354: since linux_5_4_0-40.44

-------------------------------------------------------------------------------
If you use vendor_db functionality of providing multiple certificates and/or
hashes please briefly describe your certificate setup. If there are whitelisted hashes
please provide exact binaries for which hashes are created via file sharing service,
available in public with anonymous access for verification
-------------------------------------------------------------------------------

Not used, no binaries whitelisted

-------------------------------------------------------------------------------
What OS and toolchain must we use to reproduce this build?  Include where to find it, etc.  We're going to try to reproduce your build as close as possible to verify that it's really a build of the source tree you tell us it is, so these need to be fairly thorough. At the very least include the specific versions of gcc, binutils, and gnu-efi which were used, and where to find those binaries.
-------------------------------------------------------------------------------
We use Debian Buster as build environment for shim

Gcc:        8.3.0 (Debian 8.3.0-6)
Binutils:   2.31  (2.31.1-16)
gnu-efi:    3.0.9 (3.0.9-1)
sbsigntool: 0.9.2-2
lcab:       1.0b12-7

for getting the sources we use 
git-core:   2.20.1 (1:2.20.1-2+deb10u3)
git:        2.20.1 (1:2.20.1-2+deb10u3)


sbsigntool is used instead of pesign
lcab is used to pack shim into a cab file

To build the shim you can checkout 
https://github.com/Toolhouse-DV-Systeme/build_shim/tree/master and use the
build_shim script
You will need the public part of a certificate and update the CERT variable 
in the script
When run the script will check out the toolhouse-15.1 repository into a subdirectory,
copy the certificate and build shim
As a result you will get a shim_toolhouse_x64.efi file and a cab file with the efi 
file renamed to BOOTX64.EFI (This was the way to send the file to Microsoft)


-------------------------------------------------------------------------------
Which files in this repo are the logs for your build?   This should include logs for creating the buildroots, applying patches, doing the build, creating the archives, etc.
-------------------------------------------------------------------------------
The file 'build.log' holds the complete build run, starting with cleanup of old files, checkout, build and packaging the built file into a .cab file

-------------------------------------------------------------------------------
Add any additional information you think we may need to validate this shim
-------------------------------------------------------------------------------
Sha256 hash: 0bce3e7af4aa1658025ef88a6c2d9e615c250d3f41fe6f3b1bfc28cfc5431af1
