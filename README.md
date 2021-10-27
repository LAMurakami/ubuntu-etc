# Ubuntu Server 20.04 configuration changes for LAM AWS VPC EC2 instances

The [LAM AWS EC2 CloudInit](https://github.com/LAMurakami/aws#readme)
builds a LAMP model web service software stack instance from
the Latest Ubuntu Server image available.  This repo contains the
/etc files changed in the CloudInit process as well as a branch
representing additional changes for the main server.

The ubuntu-etc repo is built starting with
[a .gitignore everything file](https://github.com/LAMurakami/ubuntu-etc/blob/master/.gitignore)
and then adding exceptions for files to be added to the repo.

I created the ubuntu-etc repo populating it first from a freshly
launched lam1 instance, then from a lam2 instance, and then from
the current main aws instance.  Once published I can point to
the diff output of a particular commit and more.

I had originally created this as a private repo but as I was
thinking of the documentation uses I realized how much more
valuable it is if the documentation is public.  So I uploaded
the repo into an empty ubuntu-etc repo going through
some extra steps to get all three of the initial branches I have
created uploaded.  I actually cloned the repo to /tmp and uploaded
the clone which allowed me to do it as an regular user and ignore
the extra steps involving sudo as well as switch branches at will
without it affecting a machines configuration.  I noticed I like
the URLs at github which has &lt;repo&gt;/commit/&lt;commit-ID&gt; instead
of p=&lt;repo&gt;;a=commit;&lt;commit-ID&gt; and such.  I may want to
investigate Rewrite rules to accomplish this.

The [etckeeper](https://ubuntu.com/server/docs/tools-etckeeper)
package from the Ubuntu repositories is actually used on my
machines with git as it's Version Control System.  I like
that it is integrated with the Ubuntu apt package manager
and by default does commits for each package install or
upgrade that makes etc changes.  Although access to the
AWS EC2 instances is by ssh public keys and password
authentication is not enabled I still wasn't sure I wanted
all /etc files published to all and am sure it is not best
practice.

Below are links to the significant commits that created the
[ubuntu-etc/branches](https://github.com/LAMurakami/ubuntu-etc/branches):

* [4 Changed files to make the main lam1 instance](https://github.com/LAMurakami/ubuntu-etc/commit/d0297ec)
* [2 Changed files to make the main lam2 instance](https://github.com/LAMurakami/ubuntu-etc/compare/lam2)
* [12 Changed files to make the main aws instance](https://github.com/LAMurakami/ubuntu-etc/compare/aws)
