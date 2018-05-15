---
title: '&lt;transportConfigurationTypes&gt;'
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 422de17f4c1b42579eadc16c7ec1a0037903d1a9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="627a7-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="627a7-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="627a7-103">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="627a7-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="627a7-104">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="627a7-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="627a7-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="627a7-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="627a7-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="627a7-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="627a7-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="627a7-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="627a7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="627a7-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="627a7-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="627a7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="627a7-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="627a7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="627a7-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="627a7-111">Attributes</span></span>  
  
|<span data-ttu-id="627a7-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="627a7-112">Attribute</span></span>|<span data-ttu-id="627a7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="627a7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="627a7-114">name</span><span class="sxs-lookup"><span data-stu-id="627a7-114">name</span></span>|<span data-ttu-id="627a7-115">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="627a7-115">The name of the transport</span></span>|  
|<span data-ttu-id="627a7-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="627a7-116">transportConfigurationType</span></span>|<span data-ttu-id="627a7-117">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="627a7-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="627a7-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="627a7-118">Child Elements</span></span>  
  
|<span data-ttu-id="627a7-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="627a7-119">Element</span></span>|<span data-ttu-id="627a7-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="627a7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="627a7-121">\<add></span><span class="sxs-lookup"><span data-stu-id="627a7-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="627a7-122">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="627a7-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="627a7-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="627a7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="627a7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="627a7-124">Element</span></span>|<span data-ttu-id="627a7-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="627a7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="627a7-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="627a7-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="627a7-127">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="627a7-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="627a7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="627a7-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="627a7-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="627a7-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
