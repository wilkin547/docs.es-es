---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788250"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="6179b-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="6179b-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="6179b-102">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="6179b-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="6179b-103">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="6179b-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="6179b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6179b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6179b-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="6179b-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="6179b-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="6179b-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6179b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6179b-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6179b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6179b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6179b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6179b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6179b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6179b-110">Attributes</span></span>  
  
|<span data-ttu-id="6179b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6179b-111">Attribute</span></span>|<span data-ttu-id="6179b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6179b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6179b-113">name</span><span class="sxs-lookup"><span data-stu-id="6179b-113">name</span></span>|<span data-ttu-id="6179b-114">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="6179b-114">The name of the transport</span></span>|  
|<span data-ttu-id="6179b-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="6179b-115">transportConfigurationType</span></span>|<span data-ttu-id="6179b-116">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="6179b-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6179b-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6179b-117">Child Elements</span></span>  
  
|<span data-ttu-id="6179b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6179b-118">Element</span></span>|<span data-ttu-id="6179b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="6179b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6179b-120">\<add></span><span class="sxs-lookup"><span data-stu-id="6179b-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="6179b-121">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="6179b-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6179b-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6179b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6179b-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="6179b-123">Element</span></span>|<span data-ttu-id="6179b-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="6179b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6179b-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="6179b-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="6179b-126">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="6179b-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6179b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6179b-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="6179b-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="6179b-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
