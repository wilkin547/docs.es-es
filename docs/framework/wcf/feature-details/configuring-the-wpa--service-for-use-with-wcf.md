---
description: Más información acerca de cómo configurar el servicio de activación de procesos de Windows para su uso con Windows Communication Foundation
title: Configuración del Servicio de activación de procesos de Windows para el uso con Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
ms.openlocfilehash: b98cc776b3a0bd860b4837ba70d58d10a83827dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780627"
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a><span data-ttu-id="9c5ab-103">Configuración del Servicio de activación de procesos de Windows para el uso con Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9c5ab-103">Configuring the Windows Process Activation Service for Use with Windows Communication Foundation</span></span>

<span data-ttu-id="9c5ab-104">En este tema se describen los pasos necesarios para configurar el servicio de activación de procesos de Windows (también conocido como WAS) en Windows Vista para hospedar servicios Windows Communication Foundation (WCF) que no se comunican a través de protocolos de red HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-104">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) in Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="9c5ab-105">Las siguientes secciones describen los pasos para realizar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="9c5ab-105">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="9c5ab-106">Instale (o confirme la instalación de) los componentes de activación de WCF requeridos.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-106">Install (or confirm the installation of) the WCF activation components required.</span></span>  
  
- <span data-ttu-id="9c5ab-107">Cree un sitio WAS con los enlaces de protocolos de red que desee utilizar o agregue un nuevo enlace de protocolo a un sitio existente.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-107">Create a WAS site with the network protocol bindings you wish to use, or add a new protocol binding to an existing site.</span></span>  
  
- <span data-ttu-id="9c5ab-108">Cree una aplicación para hospedar sus servicios y permita a esa aplicación utilizar los protocolos de red necesarios.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-108">Create an application to host your services and enable that application to use the required network protocols.</span></span>  
  
- <span data-ttu-id="9c5ab-109">Cree un servicio WCF que exponga un punto de conexión que no sea HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-109">Build a WCF service that exposes a non-HTTP endpoint.</span></span>  
  
## <a name="configuring-a-site-with-non-http-bindings"></a><span data-ttu-id="9c5ab-110">Configuración de un sitio con enlaces que no sean HTTP</span><span class="sxs-lookup"><span data-stu-id="9c5ab-110">Configuring a Site with Non-HTTP bindings</span></span>  

 <span data-ttu-id="9c5ab-111">Para utilizar un enlace no HTTP con WAS, el enlace del sitio se debe agregar a la configuración de WAS.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-111">To use a non-HTTP binding with WAS, the site binding must be added to the WAS configuration.</span></span> <span data-ttu-id="9c5ab-112">El almacén de configuración para WAS es el archivo applicationHost.config, ubicado en el directorio %windir%\system32\inetsrv\config.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-112">The configuration store for WAS is the applicationHost.config file, located in the %windir%\system32\inetsrv\config directory.</span></span> <span data-ttu-id="9c5ab-113">WAS e IIS 7.0 comparten este almacén de configuración.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-113">This configuration store is shared by both WAS and IIS 7.0.</span></span>  
  
 <span data-ttu-id="9c5ab-114">applicationHost.config es un archivo de texto XML que se puede abrir con cualquier editor de texto estándar (como el Bloc de notas).</span><span class="sxs-lookup"><span data-stu-id="9c5ab-114">applicationHost.config is an XML text file that can be opened with any standard text editor (such as Notepad).</span></span> <span data-ttu-id="9c5ab-115">Sin embargo, la herramienta de configuración de línea de comandos (appcmd.exe) de IIS 7,0 es la manera preferida de agregar enlaces de sitios que no son HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-115">However, the IIS 7.0 command-line configuration tool (appcmd.exe) is the preferred way to add non-HTTP site bindings.</span></span>  
  
 <span data-ttu-id="9c5ab-116">El siguiente comando agrega un enlace de sitio net.tcp al sitio web predeterminado utilizando appcmd.exe (este comando se escribe como una línea única).</span><span class="sxs-lookup"><span data-stu-id="9c5ab-116">The following command adds a net.tcp site binding to the default Web site using appcmd.exe (this command is entered as a single line).</span></span>  
  
```console  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 <span data-ttu-id="9c5ab-117">Este comando agrega el nuevo enlace net.tcp al sitio web predeterminado agregando la línea indicada a continuación al archivo applicationHost.config.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-117">This command adds the new net.tcp binding to the default Web site by adding the line indicated below to the applicationHost.config file.</span></span>  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a><span data-ttu-id="9c5ab-118">Permitir a una aplicación que utilice protocolos no HTTP</span><span class="sxs-lookup"><span data-stu-id="9c5ab-118">Enabling an Application to Use Non-HTTP Protocols</span></span>  

 <span data-ttu-id="9c5ab-119">Puede habilitar o deshabilitar protocolsat de red individuales el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-119">You can enable or disable individual network protocolsat the application level.</span></span> <span data-ttu-id="9c5ab-120">El siguiente comando muestra cómo habilitar los protocolos HTTP y net.tcp para una aplicación que se ejecute en el `Default Web Site`.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-120">The following command illustrates how to enable both the HTTP and net.tcp protocols for an application that runs in the `Default Web Site`.</span></span>  
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 <span data-ttu-id="9c5ab-121">La lista de protocolos habilitados también se puede establecer en el \<applicationDefaults> elemento de la configuración XML del sitio almacenado en ApplicationHost.config.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-121">The list of enabled protocols can also be set in the \<applicationDefaults> element of the site’s XML configuration stored in ApplicationHost.config.</span></span>  
  
 <span data-ttu-id="9c5ab-122">El siguiente código XML de applicationHost.config muestra un sitio enlazado a protocolos HTTP y no HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-122">The following XML code from applicationHost.config illustrates a site bound to both HTTP and non-HTTP protocols.</span></span> <span data-ttu-id="9c5ab-123">Se llama a la configuración adicional necesaria para admitir protocolos no HTTP mediante comentarios.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-123">The additional configuration required to support non-HTTP protocols is called out with comments.</span></span>  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
      <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
      </application>  
      <bindings>  
            <!-- The following two lines are added by the command. -->
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults
      applicationPool="DefaultAppPool"
      <!-- The following line is inserted by the command. -->
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 <span data-ttu-id="9c5ab-124">Si intenta activar un servicio mediante WAS para la activación no HTTP y no ha instalado y configurado WAS, puede ver el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="9c5ab-124">If you attempt to activate a service using WAS for Non-HTTP activation and you have not installed and configured WAS you may see the following error:</span></span>  
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 <span data-ttu-id="9c5ab-125">Si ve este error, asegúrese de que WAS para la activación no HTTP está instalado y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-125">If you see this error ensure WAS for Non-HTTP Activation is installed and configured properly.</span></span> <span data-ttu-id="9c5ab-126">Para obtener más información, vea [Cómo: instalar y configurar los componentes de activación de WCF](how-to-install-and-configure-wcf-activation-components.md).</span><span class="sxs-lookup"><span data-stu-id="9c5ab-126">For more information, see [How to: Install and Configure WCF Activation Components](how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a><span data-ttu-id="9c5ab-127">Creación de un servicio WCF que utiliza WAS para la activación no HTTP</span><span class="sxs-lookup"><span data-stu-id="9c5ab-127">Building a WCF Service That Uses WAS for Non-HTTP activation</span></span>  

 <span data-ttu-id="9c5ab-128">Una vez que realice los pasos para instalar y configurar WAS (consulte [Cómo: instalar y configurar los componentes de activación de WCF](how-to-install-and-configure-wcf-activation-components.md)), la configuración de un servicio para su activación es similar a la configuración de un servicio que se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="9c5ab-128">Once you perform the steps to install and configure WAS (see [How to: Install and Configure WCF Activation Components](how-to-install-and-configure-wcf-activation-components.md)), configuring a service to use WAS for activation is similar to configuring a service that is hosted in IIS.</span></span>  
  
 <span data-ttu-id="9c5ab-129">Para obtener instrucciones detalladas sobre cómo crear un servicio WCF activado, consulte [Cómo: hospedar un servicio WCF en was](how-to-host-a-wcf-service-in-was.md).</span><span class="sxs-lookup"><span data-stu-id="9c5ab-129">For detailed instructions about building a WAS-activated WCF service, see [How to: Host a WCF Service in WAS](how-to-host-a-wcf-service-in-was.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5ab-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c5ab-130">See also</span></span>

- [<span data-ttu-id="9c5ab-131">Hospedaje en Servicio de activación de procesos de Windows</span><span class="sxs-lookup"><span data-stu-id="9c5ab-131">Hosting in Windows Process Activation Service</span></span>](hosting-in-windows-process-activation-service.md)
- <span data-ttu-id="9c5ab-132">[Características de hospedaje de Windows Server AppFabric](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="9c5ab-132">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
