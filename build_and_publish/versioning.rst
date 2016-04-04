.. versioning:

Some questions to think about when deciding whether and how to version
========================================================
* Who is using the API and what features are they using?  How painful will a version change be for them?
* Can you make your API versionless?  (Many of the web's most used API's are either versionless, or have never moved passed version 1.0.  The publisher effectively guarantees complete backward compatibility.)
* Can you create a mediation layer in the request and response pipeline that transforms requests and responses between old and new API versions?  If so, do you really need a new version in the first place?

If you decide to use versions
=============================

Never release an API without a version number.

Versions should be integers, not decimal numbers, prefixed with ‘v’. For example: 

.. Noooooo! use SemVer.org
   Single digit versions are backwards-incompatile design changes
   Double digit versions (major and minor parts) are different feature-sets, different interface specifications, that aim to be forwards compatible within the same Major (but caveat-empour)
   Tripple digit versions are same feature set, same interface spec but different "release" - functionality is not exactly the same, bugs fixed. 

Good: v1, v2, v3

Bad: v-1.1, v1.2, 1.3

Maintain APIs at least one version back.

Some questions to think about:

* What technique will you use to define the version number?  Will you include it in the URL?  Will you check the Content Type in the Accept header of requests?
* Will you have a versionless endpoint that points to the latest version?

