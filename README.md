puppet-git-hooks
================

githooks(5) scripts to work with repositories of Puppet code.


Installation
------------

Just copy the scripts to your repository into the `.git/hooks/` directory.
Make sure that the filename conforms to one of the hooks listed in
[githooks(5)](http://git-scm.com/docs/githooks) and that the executable bit
has been set.


Hooks
-----
**pre-commit:**

This pre-commit hook verifies that Puppet can parse \*.pp files (using `puppet parser validate`),
that the manifests conform to the [Puppet Labs style guide](http://docs.puppetlabs.com/guides/style_guide.html),
that YAML files are parseable, and that templates (\*.erb) have valid syntax.

The commit hook can be configured with the following environment variables:

* `PUPPETLINT_FLAGS`: Command line parameters for [puppet-lint](http://puppet-lint.com/), 
  default: `--no-autoloader_layout-check --no-80chars-check`
* `TMPDIR`: The directory in which temporary files should be written, default: `/tmp`


Support
-------

Please create bug reports and feature requests in [GitHub issues](https://github.com/gini/puppet-git-hooks/issues).


Continuous Integration
----------------------

[![Build Status](https://secure.travis-ci.org/gini/puppet-git-hooks.png)](http://travis-ci.org/gini/puppet-git-hooks)


License
-------
Copyright (c) 2012-2013 smarchive GmbH, 2013 Gini GmbH

This script is licensed under the Apache License, Version 2.0.

See http://www.apache.org/licenses/LICENSE-2.0.html for the full license text.
