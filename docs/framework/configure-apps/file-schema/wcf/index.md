---
title: Esquema de configuración de WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: 160be2ea43d1530cdb2ccd3de1f9e6a2e4d0aca3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536397"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="12200-102">Esquema de configuración de WCF</span><span class="sxs-lookup"><span data-stu-id="12200-102">WCF Configuration Schema</span></span>
<span data-ttu-id="12200-103">Los elementos de configuración de Windows Communication Foundation (WCF) le permiten configurar el servicio WCF y las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="12200-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="12200-104">Puede usar la [herramienta Editor de configuración (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) para crear y modificar los archivos de configuración para clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="12200-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="12200-105">Puesto que los archivos de certificado tiene el formato como XML, debe familiarizarse con XML si desea modificarlos manualmente con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="12200-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="12200-106">De lo contrario, puede encontrarse con problemas como no encontrar un atributo o una etiqueta de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="12200-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="12200-107">Esto se debe a que los atributos y las etiquetas del elemento XML distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="12200-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="12200-108">El sistema de configuración de WCF se basa en el <xref:System.Configuration> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="12200-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="12200-109">Por consiguiente, puede usar todas las características estándar proporcionadas por el espacio de nombres <xref:System.Configuration>, como el bloqueo de configuración, el cifrado y la combinación para aumentar la seguridad de su aplicación y su configuración.</span><span class="sxs-lookup"><span data-stu-id="12200-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="12200-110">Para obtener más información acerca del uso de estos conceptos, consulte los temas siguientes.</span><span class="sxs-lookup"><span data-stu-id="12200-110">For more information on these concepts, see the following topics.</span></span>  
  
 <span data-ttu-id="12200-111">[Cifrar información de configuración](/previous-versions/aspnet/53tyfkaw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="12200-111">[Encrypting Configuration Information](/previous-versions/aspnet/53tyfkaw(v=vs.100))</span></span>  
  
 <span data-ttu-id="12200-112">[Bloquear opciones de configuración](/previous-versions/aspnet/55th21y4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="12200-112">[Locking Configuration Settings](/previous-versions/aspnet/55th21y4(v=vs.100))</span></span>  
  
 <span data-ttu-id="12200-113">En esta sección se describen todos los valores posibles de cada elemento de configuración y cómo interactúa con otros elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="12200-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="12200-114">En el mapa siguiente se muestra el esquema de configuración de WCF:</span><span class="sxs-lookup"><span data-stu-id="12200-114">The following map illustrates the WCF configuration schema:</span></span>  
  
 ![Diagrama que muestra el esquema de configuración de WCF.](./media/index/windows-communication-foundation-configuration-schema.gif)  
  
> [!CAUTION]
> <span data-ttu-id="12200-116">Debe proteger las secciones de configuración de WCF en los archivos de configuración de la aplicación (app.config) con las listas de Access Control (ACL) adecuadas para evitar posibles amenazas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="12200-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="12200-117">Por ejemplo, debería asegurarse de que sólo las personas adecuadas pueden tener acceso o modificar la configuración de seguridad en enlaces de la aplicación, o la sección modelo de servicio del archivo de configuración de un servicio.</span><span class="sxs-lookup"><span data-stu-id="12200-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12200-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="12200-118">In This Section</span></span>  
 [\<system.serviceModel>](system-servicemodel.md)  
 <span data-ttu-id="12200-119">Describe el elemento `ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="12200-119">Describes the `ServiceModel` element.</span></span>  
  
 [\<system.serviceModel.activation>](system-servicemodel-activation.md)  
 <span data-ttu-id="12200-120">Configura la herramienta SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="12200-120">Configures the SMSvcHost.exe tool.</span></span>  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
 <span data-ttu-id="12200-121">El elemento de nivel superior para establecer opciones al usar serializadores como <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="12200-121">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="12200-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="12200-122">Related Sections</span></span>  
 [<span data-ttu-id="12200-123">Configuring Windows Communication Foundation Applications</span><span class="sxs-lookup"><span data-stu-id="12200-123">Configuring Windows Communication Foundation Applications</span></span>](../../../wcf/configuring-services.md)  
 <span data-ttu-id="12200-124">Describe cómo configurar los clientes y servicios de WCF.</span><span class="sxs-lookup"><span data-stu-id="12200-124">Describes how to configure WCF services and clients.</span></span>
