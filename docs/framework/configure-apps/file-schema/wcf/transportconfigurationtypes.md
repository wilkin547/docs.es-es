---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: bfd2147a8e772848fc98cab7a875a51bdb53b5cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941158"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="e56de-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="e56de-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="e56de-102">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="e56de-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="e56de-103">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="e56de-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="e56de-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e56de-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e56de-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="e56de-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="e56de-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="e56de-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e56de-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e56de-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e56de-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e56de-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e56de-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e56de-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e56de-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e56de-110">Attributes</span></span>  
  
|<span data-ttu-id="e56de-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e56de-111">Attribute</span></span>|<span data-ttu-id="e56de-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e56de-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e56de-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="e56de-113">name</span></span>|<span data-ttu-id="e56de-114">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="e56de-114">The name of the transport</span></span>|  
|<span data-ttu-id="e56de-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="e56de-115">transportConfigurationType</span></span>|<span data-ttu-id="e56de-116">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="e56de-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e56de-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e56de-117">Child Elements</span></span>  
  
|<span data-ttu-id="e56de-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e56de-118">Element</span></span>|<span data-ttu-id="e56de-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e56de-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e56de-120">\<add></span><span class="sxs-lookup"><span data-stu-id="e56de-120">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="e56de-121">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="e56de-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e56de-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e56de-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e56de-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e56de-123">Element</span></span>|<span data-ttu-id="e56de-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e56de-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e56de-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="e56de-125">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="e56de-126">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="e56de-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e56de-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e56de-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="e56de-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e56de-128">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
