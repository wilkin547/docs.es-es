---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854928"
---
# \<transportConfigurationTypes>
<span data-ttu-id="d3a26-101">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="d3a26-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="d3a26-102">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="d3a26-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="d3a26-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3a26-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3a26-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d3a26-104">Attributes and Elements</span></span>  
 <span data-ttu-id="d3a26-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d3a26-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3a26-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d3a26-106">Attributes</span></span>  
  
|<span data-ttu-id="d3a26-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="d3a26-107">Attribute</span></span>|<span data-ttu-id="d3a26-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3a26-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3a26-109">name</span><span class="sxs-lookup"><span data-stu-id="d3a26-109">name</span></span>|<span data-ttu-id="d3a26-110">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="d3a26-110">The name of the transport</span></span>|  
|<span data-ttu-id="d3a26-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="d3a26-111">transportConfigurationType</span></span>|<span data-ttu-id="d3a26-112">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="d3a26-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3a26-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d3a26-113">Child Elements</span></span>  
  
|<span data-ttu-id="d3a26-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3a26-114">Element</span></span>|<span data-ttu-id="d3a26-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3a26-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="d3a26-116">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="d3a26-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3a26-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d3a26-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d3a26-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3a26-118">Element</span></span>|<span data-ttu-id="d3a26-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3a26-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="d3a26-120">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="d3a26-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3a26-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3a26-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="d3a26-122">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d3a26-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
