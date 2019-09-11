---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854928"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="868e0-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="868e0-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="868e0-102">Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="868e0-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="868e0-103">Esto se puede usar para agregar protocolos WAS personalizados.</span><span class="sxs-lookup"><span data-stu-id="868e0-103">This can be used to add custom WAS protocols.</span></span>  
  
<span data-ttu-id="868e0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="868e0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="868e0-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="868e0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="868e0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceHostingEnvironment**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="868e0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="868e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> transportConfigurationTypes**</span><span class="sxs-lookup"><span data-stu-id="868e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="868e0-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="868e0-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="868e0-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="868e0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="868e0-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="868e0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="868e0-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="868e0-111">Attributes</span></span>  
  
|<span data-ttu-id="868e0-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="868e0-112">Attribute</span></span>|<span data-ttu-id="868e0-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="868e0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="868e0-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="868e0-114">name</span></span>|<span data-ttu-id="868e0-115">Nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="868e0-115">The name of the transport</span></span>|  
|<span data-ttu-id="868e0-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="868e0-116">transportConfigurationType</span></span>|<span data-ttu-id="868e0-117">El tipo que implementa el transporte.</span><span class="sxs-lookup"><span data-stu-id="868e0-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="868e0-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="868e0-118">Child Elements</span></span>  
  
|<span data-ttu-id="868e0-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="868e0-119">Element</span></span>|<span data-ttu-id="868e0-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="868e0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="868e0-121">\<add></span><span class="sxs-lookup"><span data-stu-id="868e0-121">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="868e0-122">Agrega un elemento de configuración que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="868e0-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="868e0-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="868e0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="868e0-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="868e0-124">Element</span></span>|<span data-ttu-id="868e0-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="868e0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="868e0-126">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="868e0-126">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="868e0-127">Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="868e0-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="868e0-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="868e0-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="868e0-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="868e0-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
