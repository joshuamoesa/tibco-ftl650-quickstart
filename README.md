# TIBCO FTL 6.5.0 QuickStart

Setting up, starting, and running various TIBCO FTL sample programs that demonstrate typical messaging functionality.

## Agenda
- Intro
- Get stuff: QuickStart guide, FTL software. Optional: TIBCO BWCE, Java 1.8 software (for Java samples)
- Install FTL software
- Initial configuration
- Run samples

## Intro

- [FTL product page](https://www.tibco.com/products/tibco-ftl)
- [Product Overview](https://docs.tibco.com/pub/ftl/6.5.0/doc/html/GUID-3E90C56D-AB0C-4FA6-B238-006C6766D377.html)
- [Brief definition of Key Concepts](https://docs.tibco.com/pub/ftl/6.5.0/doc/html/GUID-25FF076F-FF66-4A21-B060-56E5EB93606B.html)
- [Durables](https://postnl.atlassian.net/wiki/spaces/ESB/pages/616171175/Chapter+2+FTL#Durables)

## Stuff

### Guide
[TIBCO FTL 6.5.0 QuickStart guide](https://community.tibco.com/sites/default/files/wiki_files/tibco_ftl_quick_start_guide_6_3_0.pdf)

### Software

#### FTL 6.5.0 
- [Windows](https://jmoesa.stackstorage.com/s/angdcxyFslsu7UCq) (160 MB)
- [Linux](https://jmoesa.stackstorage.com/s/ESZNrj72SZfUxm8X) (558 MB)
- [macOS](https://jmoesa.stackstorage.com/s/Z7nMbBpHna1QQkB5) (174 MB)

#### TIBCO BusinessWorks ContainerEdition v2.5.1 (BWCE) - OPTIONAL
- [macOS](https://jmoesa.stackstorage.com/s/LfJPFTN8scHtQESs)

#### TIBCO AMX BusinessWorks Plug-in for TIBCO FTL - OPTIONAL
- [macOS](https://jmoesa.stackstorage.com/s/LBMkud8Fjn3fBWBW)

## Initial configuration

### macOS and Ubuntu

The samples in the guide use the environment variable TIBCO_HOME to point to the directory where
TIBCO FTL is installed. Set the TIBCO_HOME environment variable:
```
export TIBCO_HOME=/opt/tibco
```

Setting up your PATH for easier execution of the sample programs:
```
PATH=$PATH:$TIBCO_HOME/ftl/6.5/bin
PATH=$PATH:$TIBCO_HOME/ftl/6.5/samples/bin
PATH=$PATH:$TIBCO_HOME/ftl/6.5/samples/bin/advanced
PATH=$PATH:$TIBCO_HOME/ftl/6.5/samples/scripts

printenv PATH
```
## Starting and stopping FTL servers

### Start and stop single server
```
ftlstart ftls1@localhost:8585
ftlstop ftls1@localhost:8585
```

### Start and stop cluster of servers
```
ftlstart ftls1@localhost:8585 ftls2@localhost:8686 ftls3@localhost:8787
ftlstop ftls1@localhost:8585 ftls2@localhost:8686 ftls3@localhost:8787
```

### Start and stop a satellite server
```
ftlstart ftl_sat@localhost:8686 --satelliteof ftls1@localhost:8585
```
[Server Roles](https://docs.tibco.com/pub/ftl/6.5.0/doc/html/GUID-3E163A24-D482-44EB-8D4E-B4672EBA3340.html)

## Run samples

### Basic Publish-Subscribe sample

Show the Java code of receiver and sender. Note the contentmatcher. 

Start receiver
```
cd $TIBCO_HOME/ftl/current-version/samples/bin

tibftlrecv localhost:8585

```
Show the client in the Realm service.

In another terminal, start sender
```
cd $TIBCO_HOME/ftl/current-version/samples/bin

tibftlsend localhost:8585

```

## References
- [TIBCO FTL - Enterprise Edition 6.5.0 Product Documentation](https://docs.tibco.com/products/tibco-ftl-enterprise-edition-6-5-0)
- [TIBCO eDelivery TIBCO FTL - Enterprise Edition download location](https://edelivery.tibco.com/storefront/view-download.ep?sku=10446-3&version=6.5.0)
- [TIBCO FTL QuickStart Guides](https://community.tibco.com/wiki/tibco-ftlr-quick-start-guides)
