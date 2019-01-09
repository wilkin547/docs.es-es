---
title: '&lt;transportConfigurationTypes&gt;'
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 5a51450d198ea395098f8a6a38d9104d0fe8538b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145476"
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="cc880-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="cc880-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="cc880-103">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="cc880-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="cc880-104">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="cc880-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="cc880-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cc880-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="cc880-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="cc880-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="cc880-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="cc880-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc880-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc880-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc880-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cc880-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cc880-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cc880-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc880-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc880-111">Attributes</span></span>  
  
|<span data-ttu-id="cc880-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="cc880-112">Attribute</span></span>|<span data-ttu-id="cc880-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc880-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc880-114">name</span><span class="sxs-lookup"><span data-stu-id="cc880-114">name</span></span>|<span data-ttu-id="cc880-115">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="cc880-115">The name of the transport</span></span>|  
|<span data-ttu-id="cc880-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="cc880-116">transportConfigurationType</span></span>|<span data-ttu-id="cc880-117">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="cc880-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc880-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cc880-118">Child Elements</span></span>  
  
|<span data-ttu-id="cc880-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc880-119">Element</span></span>|<span data-ttu-id="cc880-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc880-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc880-121">\<add></span><span class="sxs-lookup"><span data-stu-id="cc880-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="cc880-122">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="cc880-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc880-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cc880-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cc880-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc880-124">Element</span></span>|<span data-ttu-id="cc880-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc880-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc880-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="cc880-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="cc880-127">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="cc880-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc880-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc880-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="cc880-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="cc880-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
