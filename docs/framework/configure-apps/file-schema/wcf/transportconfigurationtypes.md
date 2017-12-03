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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa136f75fda4a87171a8ca3e369e7cb8621ac398
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="576d5-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="576d5-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="576d5-103">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="576d5-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="576d5-104">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="576d5-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="576d5-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="576d5-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="576d5-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="576d5-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="576d5-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="576d5-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="576d5-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="576d5-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="576d5-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="576d5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="576d5-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="576d5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="576d5-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="576d5-111">Attributes</span></span>  
  
|<span data-ttu-id="576d5-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="576d5-112">Attribute</span></span>|<span data-ttu-id="576d5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="576d5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="576d5-114">name</span><span class="sxs-lookup"><span data-stu-id="576d5-114">name</span></span>|<span data-ttu-id="576d5-115">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="576d5-115">The name of the transport</span></span>|  
|<span data-ttu-id="576d5-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="576d5-116">transportConfigurationType</span></span>|<span data-ttu-id="576d5-117">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="576d5-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="576d5-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="576d5-118">Child Elements</span></span>  
  
|<span data-ttu-id="576d5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="576d5-119">Element</span></span>|<span data-ttu-id="576d5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="576d5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="576d5-121">\<add></span><span class="sxs-lookup"><span data-stu-id="576d5-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="576d5-122">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="576d5-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="576d5-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="576d5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="576d5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="576d5-124">Element</span></span>|<span data-ttu-id="576d5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="576d5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="576d5-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="576d5-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="576d5-127">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="576d5-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="576d5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="576d5-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="576d5-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="576d5-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
