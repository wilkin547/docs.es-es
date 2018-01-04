---
title: "Configuración del Servicio de activación de procesos de Windows para el uso con Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12df9e3760774b4dc8d4e8f73a09df5e79c2453e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a><span data-ttu-id="d7e7b-102">Configuración del Servicio de activación de procesos de Windows para el uso con Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d7e7b-102">Configuring the Windows Process Activation Service for Use with Windows Communication Foundation</span></span>
<span data-ttu-id="d7e7b-103">En este tema se describen los pasos necesarios para configurar el Servicio de activación de procesos de Windows (también conocido como WAS) en [!INCLUDE[wv](../../../../includes/wv-md.md)] para hospedar servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que no se comunican sobre protocolos de red HTTP.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) in [!INCLUDE[wv](../../../../includes/wv-md.md)] to host [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="d7e7b-104">Las siguientes secciones describen los pasos para realizar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="d7e7b-104">The following sections outline the steps for this configuration:</span></span>  
  
-   <span data-ttu-id="d7e7b-105">Instale (o confirme la instalación de) los componentes de activación requeridos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7e7b-105">Install (or confirm the installation of) the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] activation components required.</span></span>  
  
-   <span data-ttu-id="d7e7b-106">Cree un sitio WAS con los enlaces de protocolos de red que desee utilizar o agregue un nuevo enlace de protocolo a un sitio existente.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-106">Create a WAS site with the network protocol bindings you wish to use, or add a new protocol binding to an existing site.</span></span>  
  
-   <span data-ttu-id="d7e7b-107">Cree una aplicación para hospedar sus servicios y permita a esa aplicación utilizar los protocolos de red necesarios.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-107">Create an application to host your services and enable that application to use the required network protocols.</span></span>  
  
-   <span data-ttu-id="d7e7b-108">Cree un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que exponga un extremo que no sea HTTP.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-108">Build a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that exposes a non-HTTP endpoint.</span></span>  
  
## <a name="configuring-a-site-with-non-http-bindings"></a><span data-ttu-id="d7e7b-109">Configuración de un sitio con enlaces que no sean HTTP</span><span class="sxs-lookup"><span data-stu-id="d7e7b-109">Configuring a Site with Non-HTTP bindings</span></span>  
 <span data-ttu-id="d7e7b-110">Para utilizar un enlace no HTTP con WAS, el enlace del sitio se debe agregar a la configuración de WAS.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-110">To use a non-HTTP binding with WAS, the site binding must be added to the WAS configuration.</span></span> <span data-ttu-id="d7e7b-111">El almacén de configuración para WAS es el archivo applicationHost.config, ubicado en el directorio %windir%\system32\inetsrv\config.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-111">The configuration store for WAS is the applicationHost.config file, located in the %windir%\system32\inetsrv\config directory.</span></span> <span data-ttu-id="d7e7b-112">WAS e IIS 7.0 comparten este almacén de configuración.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-112">This configuration store is shared by both WAS and IIS 7.0.</span></span>  
  
 <span data-ttu-id="d7e7b-113">applicationHost.config es un archivo de texto XML que se puede abrir con cualquier editor de texto estándar (como el Bloc de notas).</span><span class="sxs-lookup"><span data-stu-id="d7e7b-113">applicationHost.config is an XML text file that can be opened with any standard text editor (such as Notepad).</span></span> <span data-ttu-id="d7e7b-114">Sin embargo, la herramienta de configuración de línea de comandos (appcmd.exe) de [!INCLUDE[iisver](../../../../includes/iisver-md.md)] es la manera preferida para agregar enlaces de sitio no HTTP.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-114">However, the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] command-line configuration tool (appcmd.exe) is the preferred way to add non-HTTP site bindings.</span></span>  
  
 <span data-ttu-id="d7e7b-115">El siguiente comando agrega un enlace de sitio net.tcp al sitio web predeterminado utilizando appcmd.exe (este comando se escribe como una línea única).</span><span class="sxs-lookup"><span data-stu-id="d7e7b-115">The following command adds a net.tcp site binding to the default Web site using appcmd.exe (this command is entered as a single line).</span></span>  
  
```  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 <span data-ttu-id="d7e7b-116">Este comando agrega el nuevo enlace net.tcp al sitio web predeterminado agregando la línea indicada a continuación al archivo applicationHost.config.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-116">This command adds the new net.tcp binding to the default Web site by adding the line indicated below to the applicationHost.config file.</span></span>  
  
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
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a><span data-ttu-id="d7e7b-117">Permitir a una aplicación que utilice protocolos no HTTP</span><span class="sxs-lookup"><span data-stu-id="d7e7b-117">Enabling an Application to Use Non-HTTP Protocols</span></span>  
 <span data-ttu-id="d7e7b-118">Puede habilitar o deshabilitar protocolsat el nivel de aplicación de red individuales.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-118">You can enable or disable individual network protocolsat the application level.</span></span> <span data-ttu-id="d7e7b-119">El siguiente comando muestra cómo habilitar los protocolos HTTP y net.tcp para una aplicación que se ejecute en el `Default Web Site`.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-119">The following command illustrates how to enable both the HTTP and net.tcp protocols for an application that runs in the `Default Web Site`.</span></span>  
  
```  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 <span data-ttu-id="d7e7b-120">La lista de protocolos habilitados también puede establecerse el \<applicationDefaults > elemento de la configuración del sitio XML almacenada en ApplicationHost.config.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-120">The list of enabled protocols can also be set in the \<applicationDefaults> element of the site’s XML configuration stored in ApplicationHost.config.</span></span>  
  
 <span data-ttu-id="d7e7b-121">El siguiente código XML de applicationHost.config muestra un sitio enlazado a protocolos HTTP y no HTTP.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-121">The following XML code from applicationHost.config illustrates a site bound to both HTTP and non-HTTP protocols.</span></span> <span data-ttu-id="d7e7b-122">Se llama a la configuración adicional necesaria para admitir protocolos no HTTP mediante comentarios.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-122">The additional configuration required to support non-HTTP protocols is called out with comments.</span></span>  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
    <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
    </application>  
       <bindings>  
            //The following two lines are added by the command.  
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
      //The following line is inserted by the command.  
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 <span data-ttu-id="d7e7b-123">Si intenta activar un servicio mediante WAS para la activación no HTTP y no ha instalado y configurado WAS, puede ver el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="d7e7b-123">If you attempt to activate a service using WAS for Non-HTTP activation and you have not installed and configured WAS you may see the following error:</span></span>  
  
```Output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 <span data-ttu-id="d7e7b-124">Si ve este error, asegúrese de que WAS para la activación no HTTP está instalado y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-124">If you see this error ensure WAS for Non-HTTP Activation is installed and configured properly.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="d7e7b-125">[Cómo: instalar y configurar componentes de activación de WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).</span><span class="sxs-lookup"><span data-stu-id="d7e7b-125"> [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a><span data-ttu-id="d7e7b-126">Creación de un servicio WCF que utiliza WAS para la activación no HTTP</span><span class="sxs-lookup"><span data-stu-id="d7e7b-126">Building a WCF Service That Uses WAS for Non-HTTP activation</span></span>  
 <span data-ttu-id="d7e7b-127">Después de realizar los pasos para instalar y configurar el servicio WAS (consulte [Cómo: instalar y configurar componentes de activación de WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), configurar un servicio para utilizar WAS para la activación es similar a configurar un servicio que se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="d7e7b-127">Once you perform the steps to install and configure WAS (see [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), configuring a service to use WAS for activation is similar to configuring a service that is hosted in IIS.</span></span>  
  
 <span data-ttu-id="d7e7b-128">Para obtener instrucciones detalladas acerca de cómo crear un objeto activado en el servicio WAS [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de servicio, vea [Cómo: hospedar un servicio WCF en WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span><span class="sxs-lookup"><span data-stu-id="d7e7b-128">For detailed instructions about building a WAS-activated [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e7b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7e7b-129">See Also</span></span>  
 [<span data-ttu-id="d7e7b-130">Hospedaje en Servicio de activación de procesos de Windows</span><span class="sxs-lookup"><span data-stu-id="d7e7b-130">Hosting in Windows Process Activation Service</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)  
 [<span data-ttu-id="d7e7b-131">Características de hospedaje de Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="d7e7b-131">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
