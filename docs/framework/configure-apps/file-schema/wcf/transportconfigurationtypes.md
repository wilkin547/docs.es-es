---
title: '&lt;transportConfigurationTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b048b160f337897765fa4fcff73a4906534ab08b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="b8527-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="b8527-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="b8527-103">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="b8527-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="b8527-104">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="b8527-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="b8527-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b8527-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b8527-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="b8527-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="b8527-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="b8527-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8527-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8527-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8527-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b8527-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b8527-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b8527-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8527-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b8527-111">Attributes</span></span>  
  
|<span data-ttu-id="b8527-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="b8527-112">Attribute</span></span>|<span data-ttu-id="b8527-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8527-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8527-114">name</span><span class="sxs-lookup"><span data-stu-id="b8527-114">name</span></span>|<span data-ttu-id="b8527-115">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="b8527-115">The name of the transport</span></span>|  
|<span data-ttu-id="b8527-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="b8527-116">transportConfigurationType</span></span>|<span data-ttu-id="b8527-117">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="b8527-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8527-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b8527-118">Child Elements</span></span>  
  
|<span data-ttu-id="b8527-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8527-119">Element</span></span>|<span data-ttu-id="b8527-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8527-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8527-121">\<add></span><span class="sxs-lookup"><span data-stu-id="b8527-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="b8527-122">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="b8527-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8527-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b8527-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b8527-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8527-124">Element</span></span>|<span data-ttu-id="b8527-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8527-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8527-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="b8527-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="b8527-127">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="b8527-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8527-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8527-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="b8527-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="b8527-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
