---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 560da96c50e99461d25c1fd65def2dc10c284470
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261677"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="498eb-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="498eb-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="498eb-102">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="498eb-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="498eb-103">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="498eb-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="498eb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="498eb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="498eb-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="498eb-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="498eb-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="498eb-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="498eb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="498eb-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="498eb-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="498eb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="498eb-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="498eb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="498eb-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="498eb-110">Attributes</span></span>  
  
|<span data-ttu-id="498eb-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="498eb-111">Attribute</span></span>|<span data-ttu-id="498eb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="498eb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="498eb-113">name</span><span class="sxs-lookup"><span data-stu-id="498eb-113">name</span></span>|<span data-ttu-id="498eb-114">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="498eb-114">The name of the transport</span></span>|  
|<span data-ttu-id="498eb-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="498eb-115">transportConfigurationType</span></span>|<span data-ttu-id="498eb-116">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="498eb-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="498eb-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="498eb-117">Child Elements</span></span>  
  
|<span data-ttu-id="498eb-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="498eb-118">Element</span></span>|<span data-ttu-id="498eb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="498eb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="498eb-120">\<add></span><span class="sxs-lookup"><span data-stu-id="498eb-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="498eb-121">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="498eb-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="498eb-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="498eb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="498eb-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="498eb-123">Element</span></span>|<span data-ttu-id="498eb-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="498eb-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="498eb-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="498eb-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="498eb-126">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="498eb-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="498eb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="498eb-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="498eb-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="498eb-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
