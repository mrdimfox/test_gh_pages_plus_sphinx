# Minimal makefile for Sphinx documentation
#

# You can set these variables from the command line, and also
# from the environment for the first two.
SPHINXOPTS    ?=
SPHINXBUILD   ?= sphinx-build
SOURCEDIR     = source
BUILDDIR      = build

ifeq ($(OS),Windows_NT)
    RM_BUILD = powershell rm ../../docs/* -Recurse
    CP_BUILD = powershell cp build/html/* ../../docs -Recurse
else
	RM_BUILD = rm -rf ../../docs/* && rm -rf ../../docs/.??*
	CP_BUILD = cp -a build/html/. ../../docs
endif

# Put it first so that "make" without argument is like "make help".
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

.PHONY: help Makefile

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
	$(RM_BUILD)
	$(CP_BUILD)