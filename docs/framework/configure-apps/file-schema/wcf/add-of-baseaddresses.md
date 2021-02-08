---
description: 'Más información sobre: <add> de <baseAddresses>'
title: <add> de <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: b25a4b5551784ecd8e67569c82c1388a144a9c9f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804067"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="fa599-103">\<add> de \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="fa599-103">\<add> of \<baseAddresses></span></span>

<span data-ttu-id="fa599-104">Representa un elemento de configuración que especifica las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="fa599-104">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="fa599-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa599-105">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="fa599-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="fa599-106">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa599-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa599-107">Attributes and Elements</span></span>  

 <span data-ttu-id="fa599-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fa599-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa599-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa599-109">Attributes</span></span>  
  
|<span data-ttu-id="fa599-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="fa599-110">Attribute</span></span>|<span data-ttu-id="fa599-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa599-111">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="fa599-112">Cadena que especifica una dirección base usada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="fa599-112">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa599-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa599-113">Child Elements</span></span>  

 <span data-ttu-id="fa599-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fa599-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa599-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa599-115">Parent Elements</span></span>  
  
|<span data-ttu-id="fa599-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa599-116">Element</span></span>|<span data-ttu-id="fa599-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa599-117">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="fa599-118">Una colección de elementos de `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="fa599-118">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa599-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa599-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="fa599-120">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="fa599-120">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
