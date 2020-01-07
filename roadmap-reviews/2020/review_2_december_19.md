# ROADMAP review (End of August '19)

We've reached the end of the first evaluation period for our 2020 roadmap, and
we are due a review of our activities. Here's a rundown of what has happened in
the scope of the in-toto project's
[ROADMAP](https://github.com/in-toto/docs/blob/master/ROADMAP.md) for this
year.

## Cross-implementation interoperability

GO
Adding ed25519 sigining https://github.com/in-toto/in-toto-golang/pull/48
Fixing canonicalization https://github.com/in-toto/in-toto-golang/pull/50

Java



## ITE

The TUF and in-toto ITE's had very little activity, as we've been working on
other fronts lately. 
For the last evaluation period we have presented two ITE drafts 
- [ITE-2: Using TUF and in-toto to build compromise-resilient CI/CD](https://github.com/in-toto/ITE/pull/4)
- [ITE-3: Real-world example of combining TUF and in-toto for packaging DataDog Agent integrations](
https://github.com/in-toto/ITE/pull/5)

In addition, and as further evidence of our commitment to integrating with
SPDX, we have a new ITE to add to the family:

- [ITE-4: Add generic URI schemes for artifacts in in-toto metadata ](https://github.com/in-toto/ITE/pull/6)

This ITE will allow in-toto to not only refer to artifacts as files, but rather
as more rich elements, such as (you guessed right) SPDX elements, or CI actions
(like GitHub's) and more!

## Maturing of existing sub-projects

### Jenkins

We have had very little activity on the Jenkins plug-in side, mostly because the
reduced feature set has had very little to update and/or fix. However, we are
brewing support for [Grafeas](https://github.com/grafeas/grafeas) as a
transport. This way, the in-toto Jenkins plug-in will be able to store in-toto
link metadata in a Grafeas server seamlessly. More to come on this front!

### Kubernetes components

As part of our work with the Grafeas adoption, we have had the chance to
evaluate a user story of the in-toto admission controller that uses Grafeas to
store link metadata (and possibly query other metadata as part of its
verification process). Although only sketches have come out so far, we are very
excited to show this to everybody once things come to fruition.

### GPG support

We started using securesystemlib's version of the gpg module. In addition, as
one of our industry partners requested, we gave the module support for
[ed25519](https://github.com/secure-systems-lab/securesystemslib/pull/188) keys
and signatures. As a result, everybody can benefit from a more feature-rich gpg
submodule.

### Apt transport and rebuilders

The apt transport and rebuilder saw a lot of work from Senior and Junior
members of the team.

- securesystemslib and in-toto have both been accepted into Debian testing and new downstream releases are constantly prepared.
https://tracker.debian.org/pkg/python-securesystemslib
https://tracker.debian.org/pkg/in-toto

- We are working hard on getting the debian apt-transport into the Debian repository and fixing bugs on the go (https://github.com/in-toto/apt-transport-in-toto/pull/26) [TODO: see mail to vagrant]

- Kristel Fung (@kristelfung) joined the team in a more-permanent fashion, and
  continued her work on making the rebuilder monitor more robust and to use the
  newer interface for buildinfos. We have continuously tested these changes on
  the rebuilder we host here at NYU.
  https://salsa.debian.org/reproducible-builds/debian-rebuilder-setup/merge_requests/2

- We attended the 5th reproducible builds summit, to discuss [TODO: See mail to justin]
  with community (Arch Linux, Debian, F-Droid, GNU Guix, MirageOS,, etc.) and industry partners (Google, Huawei, Microsoft, etc.).
  And brainstorm future collaborations.

  https://reproducible-builds.org/events/Marrakesh2019/

  [TODO: See mail to justin and santiago] 

- More news from the reproducible builds community that feature in-toto

https://reproducible-builds.org/reports/2019-09/
https://reproducible-builds.org/reports/2019-10/
https://reproducible-builds.org/reports/2019-12/




### Kubesec integration

We managed to work with the amazing team at ControlPlane, in order to provide
the ability of signing your [kubesec scans using
in-toto](https://github.com/controlplaneio/kubesec/pull/75). We believe this is
a great step forward not only to improve the security of the scanner ecosystem
(by effectively generating signed http exchanges), but to set a precedent for
other scanner services that may want to integrate in-toto --- the total diff
was around 50 lines.

## Closing remarks.

This is it for this evaluation period. This period has mostly been centered
around showing people how to use in-toto in their ecosystem. As such, we've
moved greatly in the direction of a broader industry adoption. We believe that,
before the closing ROADMAP review, we'll have many surprises to share regarding
adoption, user stories and more.
