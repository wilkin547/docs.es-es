---
description: 'Más información acerca de: esquema de configuración de WCF'
title: Esquema de configuración de WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 31307fd299cc1e0b63d92b43b33aabafa28858f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725771"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="b9e79-103">Esquema de configuración de WCF</span><span class="sxs-lookup"><span data-stu-id="b9e79-103">WCF Configuration Schema</span></span>

<span data-ttu-id="b9e79-104">Los elementos de configuración de Windows Communication Foundation (WCF) le permiten configurar el servicio WCF y las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="b9e79-104">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="b9e79-105">Puede usar la [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) para crear y modificar los archivos de configuración para clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="b9e79-105">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="b9e79-106">Puesto que los archivos de certificado tiene el formato como XML, debe familiarizarse con XML si desea modificarlos manualmente con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="b9e79-106">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="b9e79-107">De lo contrario, puede encontrarse con problemas como no encontrar un atributo o una etiqueta de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="b9e79-107">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="b9e79-108">Esto se debe a que los atributos y las etiquetas del elemento XML distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b9e79-108">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="b9e79-109">El sistema de configuración de WCF se basa en el <xref:System.Configuration> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b9e79-109">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="b9e79-110">Por consiguiente, puede usar todas las características estándar proporcionadas por el espacio de nombres <xref:System.Configuration>, como el bloqueo de configuración, el cifrado y la combinación para aumentar la seguridad de su aplicación y su configuración.</span><span class="sxs-lookup"><span data-stu-id="b9e79-110">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="b9e79-111">Para obtener más información acerca del uso de estos conceptos, consulte los temas siguientes.</span><span class="sxs-lookup"><span data-stu-id="b9e79-111">For more information on these concepts, see the following topics.</span></span>  
  
 <span data-ttu-id="b9e79-112">[Cifrar información de configuración](/previous-versions/aspnet/53tyfkaw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b9e79-112">[Encrypting Configuration Information](/previous-versions/aspnet/53tyfkaw(v=vs.100))</span></span>  
  
 <span data-ttu-id="b9e79-113">[Bloquear opciones de configuración](/previous-versions/aspnet/55th21y4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b9e79-113">[Locking Configuration Settings](/previous-versions/aspnet/55th21y4(v=vs.100))</span></span>  
  
 <span data-ttu-id="b9e79-114">En esta sección se describen todos los valores posibles de cada elemento de configuración y cómo interactúa con otros elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="b9e79-114">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="b9e79-115">En el mapa siguiente se muestra el esquema de configuración de WCF:</span><span class="sxs-lookup"><span data-stu-id="b9e79-115">The following map illustrates the WCF configuration schema:</span></span>

:::image type="content" source="./media/index/windows-communication-foundation-configuration-schema.gif" alt-text="Diagrama que muestra el esquema de configuración de WCF." lightbox="./media/index/windows-communication-foundation-configuration-schema.gif":::
  
> [!CAUTION]
> <span data-ttu-id="b9e79-117">Proteja las secciones de configuración de WCF en los archivos de configuración de la aplicación (app.config) con las listas de Access Control (ACL) adecuadas para evitar posibles amenazas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b9e79-117">Protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span> <span data-ttu-id="b9e79-118">Por ejemplo, asegúrese de que solo las personas adecuadas puedan tener acceso o modificar la configuración de seguridad en los enlaces de la aplicación, o la sección modelo de servicio del archivo de configuración de un servicio.</span><span class="sxs-lookup"><span data-stu-id="b9e79-118">For example, make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9e79-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b9e79-119">In This Section</span></span>  

 [\<system.serviceModel>](system-servicemodel.md)  
 <span data-ttu-id="b9e79-120">Describe el elemento `ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="b9e79-120">Describes the `ServiceModel` element.</span></span>  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 <span data-ttu-id="b9e79-121">Configura la herramienta SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b9e79-121">Configures the SMSvcHost.exe tool.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 <span data-ttu-id="b9e79-122">El elemento de nivel superior para establecer opciones al usar serializadores como <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b9e79-122">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b9e79-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b9e79-123">Related Sections</span></span>  

 [<span data-ttu-id="b9e79-124">Configuring Windows Communication Foundation Applications</span><span class="sxs-lookup"><span data-stu-id="b9e79-124">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="b9e79-125">Describe cómo configurar los clientes y servicios de WCF.</span><span class="sxs-lookup"><span data-stu-id="b9e79-125">Describes how to configure WCF services and clients.</span></span>
