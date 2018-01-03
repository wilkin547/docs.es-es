---
title: "Esquema de configuración de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e006cf94e9ec048617856e997271cd450725b94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="23382-102">Esquema de configuración de WCF</span><span class="sxs-lookup"><span data-stu-id="23382-102">WCF Configuration Schema</span></span>
<span data-ttu-id="23382-103">Los elementos de configuración de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] le permiten configurar el servicio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="23382-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] configuration elements enable you to configure [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service and client applications.</span></span> <span data-ttu-id="23382-104">Puede usar la [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) para crear y modificar los archivos de configuración para clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="23382-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="23382-105">Puesto que los archivos de certificado tiene el formato como XML, debe familiarizarse con XML si desea modificarlos manualmente con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="23382-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="23382-106">De lo contrario, puede encontrarse con problemas como no encontrar un atributo o una etiqueta de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="23382-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="23382-107">Esto se debe a que los atributos y las etiquetas del elemento XML distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="23382-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="23382-108">El sistema de configuración de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] se basa en el espacio de nombres <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="23382-108">The [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="23382-109">Por consiguiente, puede usar todas las características estándar proporcionadas por el espacio de nombres <xref:System.Configuration>, como el bloqueo de configuración, el cifrado y la combinación para aumentar la seguridad de su aplicación y su configuración.</span><span class="sxs-lookup"><span data-stu-id="23382-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="23382-110">Para obtener más información acerca del uso de estos conceptos, consulte los temas siguientes.</span><span class="sxs-lookup"><span data-stu-id="23382-110">For more information on these concepts, see the following topics.</span></span>  
  
 [<span data-ttu-id="23382-111">Cifrar información de configuración</span><span class="sxs-lookup"><span data-stu-id="23382-111">Encrypting Configuration Information</span></span>](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [<span data-ttu-id="23382-112">Bloquear opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="23382-112">Locking Configuration Settings</span></span>](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 <span data-ttu-id="23382-113">En esta sección se describen todos los valores posibles de cada elemento de configuración y cómo interactúa con otros elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="23382-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="23382-114">El siguiente mapa muestra el esquema de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="23382-114">The following map illustrates the WCF configuration schema.</span></span>  
  
 <span data-ttu-id="23382-115">![Esquema de configuración de WCF](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span><span class="sxs-lookup"><span data-stu-id="23382-115">![WCF Configuration Schema](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="23382-116">Debería proteger las secciones de configuración de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en sus archivos de configuración de la aplicación (app.config) con listas de control de acceso (ACL) adecuadas para evitar cualquier posible amenaza a la seguridad.</span><span class="sxs-lookup"><span data-stu-id="23382-116">You should protect [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="23382-117">Por ejemplo, debería asegurarse de que sólo las personas adecuadas pueden tener acceso o modificar la configuración de seguridad en enlaces de la aplicación, o la sección modelo de servicio del archivo de configuración de un servicio.</span><span class="sxs-lookup"><span data-stu-id="23382-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23382-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="23382-118">In This Section</span></span>  
 [<span data-ttu-id="23382-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="23382-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 <span data-ttu-id="23382-120">Describe el elemento `ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="23382-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="23382-121">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="23382-121">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 <span data-ttu-id="23382-122">Configura la herramienta SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="23382-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="23382-123">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="23382-123">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 <span data-ttu-id="23382-124">El elemento de nivel superior para establecer opciones al usar serializadores como <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="23382-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="23382-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="23382-125">Related Sections</span></span>  
 [<span data-ttu-id="23382-126">Configurar aplicaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="23382-126">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/en-us/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 <span data-ttu-id="23382-127">Describe cómo configurar los clientes y servicios de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23382-127">Describes how to configure [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services and clients.</span></span>
