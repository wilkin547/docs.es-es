---
description: 'Más información acerca de: <transportConfigurationTypes>'
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: d6ef92cf3bdd10fdc9b374f10aaa748cf4300529
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749277"
---
# \<transportConfigurationTypes>

<span data-ttu-id="ed17d-102">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="ed17d-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="ed17d-103">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="ed17d-103">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="ed17d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed17d-104">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed17d-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ed17d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ed17d-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ed17d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed17d-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ed17d-107">Attributes</span></span>  
  
|<span data-ttu-id="ed17d-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ed17d-108">Attribute</span></span>|<span data-ttu-id="ed17d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed17d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed17d-110">name</span><span class="sxs-lookup"><span data-stu-id="ed17d-110">name</span></span>|<span data-ttu-id="ed17d-111">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="ed17d-111">The name of the transport</span></span>|  
|<span data-ttu-id="ed17d-112">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="ed17d-112">transportConfigurationType</span></span>|<span data-ttu-id="ed17d-113">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="ed17d-113">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed17d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ed17d-114">Child Elements</span></span>  
  
|<span data-ttu-id="ed17d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed17d-115">Element</span></span>|<span data-ttu-id="ed17d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed17d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="ed17d-117">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="ed17d-117">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed17d-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ed17d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ed17d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed17d-119">Element</span></span>|<span data-ttu-id="ed17d-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed17d-120">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="ed17d-121">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="ed17d-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed17d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed17d-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="ed17d-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ed17d-123">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
