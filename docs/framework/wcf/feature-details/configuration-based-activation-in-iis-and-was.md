---
title: "Activación basada en la configuración en IIS y WAS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0938b98a3f079d03653df55f10c26a4a62db5bf3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="configuration-based-activation-in-iis-and-was"></a><span data-ttu-id="95300-102">Activación basada en la configuración en IIS y WAS</span><span class="sxs-lookup"><span data-stu-id="95300-102">Configuration-Based Activation in IIS and WAS</span></span>
<span data-ttu-id="95300-103">Normalmente, al hospedar un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en Internet Information Services (IIS) o el Servicio de activación de procesos de Windows (WAS), debe proporcionar un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="95300-103">Normally when hosting a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under Internet Information Services (IIS) or Windows Process Activation Service (WAS), you must provide a .svc file.</span></span> <span data-ttu-id="95300-104">El archivo .svc contiene el nombre del servicio y un generador de host de servicio personalizado opcional.</span><span class="sxs-lookup"><span data-stu-id="95300-104">The .svc file contains the name of the service and an optional custom service host factory.</span></span> <span data-ttu-id="95300-105">Este archivo adicional agrega una sobrecarga de administración.</span><span class="sxs-lookup"><span data-stu-id="95300-105">This additional file adds manageability overhead.</span></span> <span data-ttu-id="95300-106">La característica de activación basada en la configuración elimina la necesidad de tener un archivo .svc y, por lo tanto, la sobrecarga asociada.</span><span class="sxs-lookup"><span data-stu-id="95300-106">The configuration-based activation feature removes the requirement to have a .svc file and therefore the associated overhead.</span></span>  
  
## <a name="configuration-based-activation"></a><span data-ttu-id="95300-107">Activación basada en la configuración</span><span class="sxs-lookup"><span data-stu-id="95300-107">Configuration-Based Activation</span></span>  
 <span data-ttu-id="95300-108">La activación basada en la configuración toma los metadatos que se solían encontrar en el archivo .svc y los coloca en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="95300-108">Configuration-based activation takes the metadata that used to be placed in the .svc file and places it in the Web.config file.</span></span> <span data-ttu-id="95300-109">En el <`serviceHostingEnvironment`> elemento no existe un <`serviceActivations`> elemento.</span><span class="sxs-lookup"><span data-stu-id="95300-109">Within the<`serviceHostingEnvironment`> element there is a <`serviceActivations`> element.</span></span> <span data-ttu-id="95300-110">En el <`serviceActivations`> elemento son uno o más <`add`> elementos, uno para cada servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="95300-110">Within the <`serviceActivations`> element are one or more <`add`> elements, one for each hosted service.</span></span> <span data-ttu-id="95300-111">El <`add`> elemento contiene atributos que permiten definir la dirección relativa para el servicio y el tipo de servicio o un generador de host de servicio.</span><span class="sxs-lookup"><span data-stu-id="95300-111">The <`add`> element contains attributes that let you set the relative address for the service and the service type or a service host factory.</span></span> <span data-ttu-id="95300-112">El siguiente ejemplo de configuración muestra cómo se utiliza esta sección.</span><span class="sxs-lookup"><span data-stu-id="95300-112">The following configuration example code shows how this section is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95300-113">Cada <`add`> elemento debe especificar un servicio o un atributo factory.</span><span class="sxs-lookup"><span data-stu-id="95300-113">Each <`add`> element must specify a service or a factory attribute.</span></span> <span data-ttu-id="95300-114">Se puede especificar tanto el servicio como los atributos de generador.</span><span class="sxs-lookup"><span data-stu-id="95300-114">Specifying both service and factory attributes is allowed.</span></span>  
  
```xml  
<serviceHostingEnvironment>  
  <serviceActivations>  
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>  
  </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
 <span data-ttu-id="95300-115">Con esto en el archivo Web.config, puede colocar el código fuente del servicio en el directorio App_Code de la aplicación o un ensamblado compatible en el directorio Bin de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95300-115">With this in the Web.config file, you can place the service source code in the App_Code directory of the application or a complied assembly in the Bin directory of the application.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="95300-116">Cuando se usa la activación basada en la configuración, no se admite código insertado en los archivos .svc.</span><span class="sxs-lookup"><span data-stu-id="95300-116">When using configuration-based activation, inline code in .svc files is not supported.</span></span>  
> -   <span data-ttu-id="95300-117">El `relativeAddress` atributo debe establecerse en una dirección relativa como "\<subdirectorio > / service.svc" o "~ /\<subdirectorio/service.svc".</span><span class="sxs-lookup"><span data-stu-id="95300-117">The `relativeAddress` attribute must be set to a relative address such as "\<sub-directory>/service.svc" or "~/\<sub-directory/service.svc".</span></span>  
> -   <span data-ttu-id="95300-118">Se produce una excepción de configuración si registra una dirección relativa que no tiene una extensión conocida asociada a WCF.</span><span class="sxs-lookup"><span data-stu-id="95300-118">A configuration exception is thrown if you register a relative address that does not have a known extension associated with WCF.</span></span>  
> -   <span data-ttu-id="95300-119">La dirección relativa especificada es relativa a la raíz de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="95300-119">The relative address specified is relative to the root of the virtual application.</span></span>  
> -   <span data-ttu-id="95300-120">Debido al modelo jerárquico de la configuración, las direcciones relativas registradas en el equipo y en el sitio son heredadas por aplicaciones virtuales.</span><span class="sxs-lookup"><span data-stu-id="95300-120">Due to the hierarchical model of configuration, the registered relative addresses at machine and site level are inherited by virtual applications.</span></span>  
> -   <span data-ttu-id="95300-121">Los registros de un archivo de configuración tienen prioridad sobre la configuración de .svc, .xamlx, .xoml u otro archivo.</span><span class="sxs-lookup"><span data-stu-id="95300-121">Registrations in a configuration file take precedence over settings in a .svc, .xamlx, .xoml, or other file.</span></span>  
> -   <span data-ttu-id="95300-122">Cualquier '\' (barras diagonales inversas) en un URI enviada a IIS/WAS se convierte automáticamente en '/' (barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="95300-122">Any ‘\’ (backslashes) in a URI sent to IIS/WAS are automatically converted to a ‘/’ (forward slash).</span></span> <span data-ttu-id="95300-123">Si se agrega una dirección relativa que contiene una '\' y le envía a IIS un URI que usa la dirección relativa, la barra diagonal inversa se convierte en una barra diagonal e IIS no puede hacerla coincidir con la dirección relativa.</span><span class="sxs-lookup"><span data-stu-id="95300-123">If a relative address is added that contains a ‘\’ and you send IIS a URI that uses the relative address, the backslash is converted to a forward slash and IIS cannot match it to the relative address.</span></span> <span data-ttu-id="95300-124">IIS envía información de traza que indica que no se ha detectado ninguna coincidencia.</span><span class="sxs-lookup"><span data-stu-id="95300-124">IIS sends out trace information that indicates that there are no matches found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95300-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="95300-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>  
 [<span data-ttu-id="95300-126">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="95300-126">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="95300-127">Hospedar información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="95300-127">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 [<span data-ttu-id="95300-128">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="95300-128">\<serviceHostingEnvironment></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)  
 [<span data-ttu-id="95300-129">Características de hospedaje de Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="95300-129">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
