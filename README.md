
# DSpace API and JSPUI Language Packs

## Layout of the source tree

The `Messages.properties` files for each language are stored in the `src/main/resources` directory.

The file naming conventions are as follows:

`Messages_<ISO 639-1>_<ISO 3166-1>.properties`

* `ISO 639-1`: language code, in lower case.
* `ISO 3166-1`: codes for country, if required.  For example:

For example:
* `src/main/resources/``
    * `Messages.properties` - file for default (English)
    * `Messages_el.properties` - file for Greek
    * `Messages_fr_FR.properties` - file for French (France)
    * `Messages_fr_CA.properties` - file for French (Canada)


For languages that can be fully represented using the Latin-1 character set, the appropriate Messages.properties file is placed in the relevant
directory:

`src/main/resources/Messages_it.properties`

For languages that require other encodings, they are stored in this tree in
their native encoding for ease of editing, patching and so forth.  The
filename extension representing the encoding, for example:

`src/main/resources/Messages_el.properties.UTF-8`

The Maven build process supports `native2ascii` conversion on packaging of the UTF-8 files prior to packaging the jar.

## Release tags

Language packs are versioned according to the main DSpace version, but also include an incrementing `sequence-number` which allows language packs to be updated more frequently than DSpace releases.

So, DSpace software releases are of the format: `[major].[minor]` (e.g. 4.0, 4.1, 5.0, 5.1, etc.)

Whereas, DSpace language packs use the format: `[major].[minor].[sequence-number]` (e.g. 5.0.0, 5.0.1, 5.0.2 for 5.0 releases of the language packs).

Language packs are automatically installed into DSpace via Maven dependencies. In the case of the API and JSPUI language packs, they are installed as a JAR (e.g. `dspace-api-lang-[version].jar`) dependency.

## Other tools

### checkkey.pl

This is a handy Perl tool for determining which message keys are present in one properties file versus another.  This is useful for determining whether a translation is complete.  If you run:

`checkkeys.pl Messages.properties Messages_fr.properties`

the tool will tell you which keys are missing from `Messages_fr.properties`, and which (if any) are in `Messages_fr.properties` but not in the core `Messages.properties`.

In a complete translation for a particular version, there should be no missing or extra keys.

## Documentation

Additional documentation on language packs and I18N (internationalization) may be found at [Internationalization Support](https://wiki.duraspace.org/pages/viewpage.action?pageId=19006307)

Documentation for each release may be viewed online or downloaded via our [Documentation Wiki](https://wiki.duraspace.org/display/DSDOC/).

## Contributing

DSpace is a community built and supported project. We do not have a centralized development or support team,
but have a dedicated group of volunteers who help us improve the software, documentation, resources, etc.

We welcome contributions of any type. Here's a few basic guides that provide suggestions for contributing to DSpace:
* [How to Contribute to DSpace](https://wiki.duraspace.org/display/DSPACE/How+to+Contribute+to+DSpace): How to contribute in general (via code, documentation, bug reports, expertise, etc)
* [Code Contribution Guidelines](https://wiki.duraspace.org/display/DSPACE/Code+Contribution+Guidelines): How to give back code or contribute features, bug fixes, etc.
* [DSpace Community Advisory Team (DCAT)](https://wiki.duraspace.org/display/cmtygp/DSpace+Community+Advisory+Team): If you are not a developer, we also have an interest group specifically for repository managers. The DCAT group meets virtually, once a month, and sends open invitations to join their meetings via the [DCAT mailing list](https://groups.google.com/d/forum/DSpaceCommunityAdvisoryTeam).

We also encourage GitHub Pull Requests (PRs) at any time. Please see our [Development with Git](https://wiki.duraspace.org/display/DSPACE/Development+with+Git) guide for more info.

In addition, a listing of all known contributors to DSpace software can be
found online at: https://wiki.duraspace.org/display/DSPACE/DSpaceContributors

## Getting Help

DSpace provides public mailing lists where you can post questions or raise topics for discussion.
We welcome everyone to participate in these lists:

* [dspace-community@googlegroups.com](https://groups.google.com/d/forum/dspace-community) : General discussion about DSpace platform, announcements, sharing of best practices
* [dspace-tech@googlegroups.com](https://groups.google.com/d/forum/dspace-tech) : Technical support mailing list. See also our guide for [How to troubleshoot an error](https://wiki.duraspace.org/display/DSPACE/Troubleshoot+an+error).
* [dspace-devel@googlegroups.com](https://groups.google.com/d/forum/dspace-devel) : Developers / Development mailing list

Additional support options are listed at https://wiki.duraspace.org/display/DSPACE/Support

DSpace also has an active service provider network. If you'd rather hire a service provider to
install, upgrade, customize or host DSpace, then we recommend getting in touch with one of our
[Registered Service Providers](http://www.dspace.org/service-providers).

## Issue Tracker

The DSpace Issue Tracker can be found at: https://jira.duraspace.org/projects/DS/summary

## License

DSpace source code is freely available under a standard [BSD 3-Clause license](https://opensource.org/licenses/BSD-3-Clause).
The full license is available at http://www.dspace.org/license/
