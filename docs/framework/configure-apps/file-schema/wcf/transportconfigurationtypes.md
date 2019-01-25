---
title: '&lt;transportConfigurationTypes&gt;'
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 37ce20c5fb0791596264bb7b6c03d5d0f2cc2388
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704922"
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="1903c-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="1903c-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="1903c-103">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="1903c-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="1903c-104">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="1903c-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="1903c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1903c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1903c-106">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="1903c-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="1903c-107">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="1903c-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1903c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1903c-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1903c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1903c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1903c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1903c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1903c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="1903c-111">Attributes</span></span>  
  
|<span data-ttu-id="1903c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="1903c-112">Attribute</span></span>|<span data-ttu-id="1903c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1903c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1903c-114">name</span><span class="sxs-lookup"><span data-stu-id="1903c-114">name</span></span>|<span data-ttu-id="1903c-115">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="1903c-115">The name of the transport</span></span>|  
|<span data-ttu-id="1903c-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="1903c-116">transportConfigurationType</span></span>|<span data-ttu-id="1903c-117">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="1903c-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1903c-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1903c-118">Child Elements</span></span>  
  
|<span data-ttu-id="1903c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1903c-119">Element</span></span>|<span data-ttu-id="1903c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="1903c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1903c-121">\<add></span><span class="sxs-lookup"><span data-stu-id="1903c-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="1903c-122">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="1903c-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1903c-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1903c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1903c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1903c-124">Element</span></span>|<span data-ttu-id="1903c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="1903c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1903c-126">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="1903c-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="1903c-127">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="1903c-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1903c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1903c-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="1903c-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="1903c-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
