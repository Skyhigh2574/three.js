######################################################################
#
# Project specific properties.
#
# NOTE: paths must use /, not \, even on DOS. If you want to use /, use //
# Use : or ; as element seperators in path, ant can figure those out.
# NOTE you can use previously defined properties with ${prop}, but it
# must really have been defined previously
#
# Most of the properties are commented pretty well. If you can't figure them
# out, please beat Amit Singh.
#
# Any property with the list identifier in the name is a comma separated
# list of values such as directories or names.
# A example:
#   list.colors=red,blue,green,yellow
#

###############################################################################
# Most of the properties below are things that do not need to be changed      #
# unless you really know what you're doing.                                   #
###############################################################################

customer.type=FS


# Target store directory for config.xml
src.domain.config.dir=${domain.dir}/config/subscriberonline/${build.env}


# Target unix environment domain configuration
target.domain.dir=${sfs.home}/domains/weblogic/14c/subscriberonline

# Properties file location
src.properties.dir=${src.app.config.dir}/${customer.type}

# Deployment settings
has.deploy2=false
deploy1.server.name=
deploy2.server.name=
deploy1.scripts.dir=${target.build.dir}/unix/onlineserver1
deploy2.scripts.dir=
deploy.server.login=
deploy.server.keyfile=


#Target archive file

target.archive.appname=subscriberonlineapp
target.archive.filename=${target.archive.appname}.tar
target.archive.file=${target.build.dir}/archive/${target.archive.filename}
target.compressed.archive.filename=${target.archive.appname}.tar.gz
target.compressed.archive.file=${target.build.dir}/archive/${target.compressed.archive.filename}


# deploy archive file
deploy.archive.filename=${target.archive.appname}.deploy.tar
deploy.archive.file=${target.build.dir}/archive/${deploy.archive.filename}
deploy.compressed.archive.filename=${deploy.archive.filename}.gz
deploy.compressed.archive.file=${deploy.archive.file}.gz


#-------------------------------------------------------------
# subscripberApp Identity when accessing other services
#-------------------------------------------------------------
subscriber.app.username=AppSubscriber
subscriber.app.password=nj53-SEYbf-2mJr


#-------------------------------------------------------------
# Subscriber WSDl Configuration
#-------------------------------------------------------------
subscriber.wsdl.url=${subscriber.online.http}/subscriberWS/com/deltadental/subscriber/webServices/SubscriberWS.jws?WSDL

#-------------------------------------------------------------
# PreEnrollment WSDl Configuration
#-------------------------------------------------------------
preenrollment.wsdl.url=${subscriber.online.http}/subscriberWS/com/deltadental/subscriber/webServices/PreEnrollmentWS.jws?WSDL
preenrollment.wsdl.rpc.timeout=60000
preenrollment.wsdl.binding.timeout=60000

#-------------------------------------------------------------
# RightSizeDental Web Service
#-------------------------------------------------------------
rightsizedental.wsdl.url=${subscriber.online.http}/subscriberWS/com/deltadental/subscriber/webServices/RightSizeDentalWS.jws?WSDL
rightsizedental.connection.timeout=60000
rightsizedental.read.timeout=60000

#-------------------------------------------------------------
# Email Web Service configuration
#-------------------------------------------------------------

email.username=${subscriber.app.username}
email.password=${subscriber.app.password}


#-----------------------------------------------------------------------------#
# Service Locator
#-----------------------------------------------------------------------------#
subscriber.provider.url=${subscriber.online.t3}
subscriber.security.principal=${subscriber.app.username}
subscriber.security.credential=${subscriber.app.password}


#-------------------------------------------------------------
# Iebs Web Service
#-------------------------------------------------------------
iebs.wsdl.url=${iebs.online.http}/iebsWebServices/external/IebsWebService.jws?WSDL

#-------------------------------------------------------------
# IEBS commercial Web Service
#-------------------------------------------------------------
iebs.commercial.wsdl.url=${iebs.online.http}/iebsWebServices/IebsCommercialWebService?WSDL

#-----------------------------------------------------------------------------#
# From address used by EligExtract and IDCard generation process
#-----------------------------------------------------------------------------#
sms.fromaddress=sms@ddmifs.renhsc.com
sms.smtpserver=fgpcamail.ddmifs.renhsc.com
sms.smtpport=25

#-------------------------------------------------------------
# Event Service locator
#-------------------------------------------------------------
event.handler.service.user=${subscriber.app.username}
event.handler.service.password=${subscriber.app.password}

#-------------------------------------------------------------
# DCS Web Service (only valid for local, fstst2, fgptst10, fsuat2, fgpuat20)
#-------------------------------------------------------------
dcs.endpoint.url=
dcs.connection.timeout=
dcs.read.timeout=

#-----------------------------------------------------------------------------#
#********************** IEBS psp Service       ****************#
#-----------------------------------------------------------------------------#
iebs.psp.service.endpoint.url=${iebs.online.http}/iebsWS/IebsPSPWebService

#-----------------------------------------------------------------------------#
#************************ Provider List Configuration ************************#
#-----------------------------------------------------------------------------#

provider.list.wsdl.url=${provider.locator.url}/LocatorService/LocatorService.asmx?WSDL
provider.list.wsdl.rpc.timeout=60000
provider.list.wsdl.binding.timeout=60000

#-----------------------------------------------------------------------------#
#********************* Vault Configuration ***********************************#
#-----------------------------------------------------------------------------#
vault.domain=vvaultuat
vault.path=/secret/uat10/ets-subscriber-app/oidc_client 

#----------------------------------------------------------------------------------------#
#************************ Okta Configuration *********************************#
#----------------------------------------------------------------------------------------#

okta.endpoint.uri=https://auth.uat-fgp.rooseveltsolutions.com/oauth2/aus89n0nyuphhVZC51d7/v1/token
