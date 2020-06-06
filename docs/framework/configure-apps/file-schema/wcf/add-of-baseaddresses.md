---
title: <add> de <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d75142209ad8706d0cad5ce188d9d991a5e881bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850586"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="cb43c-102">\<add> de \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="cb43c-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="cb43c-103">Representa un elemento de configuración que especifica las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="cb43c-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="cb43c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb43c-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="cb43c-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="cb43c-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb43c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cb43c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cb43c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cb43c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb43c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="cb43c-108">Attributes</span></span>  
  
|<span data-ttu-id="cb43c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="cb43c-109">Attribute</span></span>|<span data-ttu-id="cb43c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb43c-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="cb43c-111">Cadena que especifica una dirección base usada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="cb43c-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb43c-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cb43c-112">Child Elements</span></span>  
 <span data-ttu-id="cb43c-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cb43c-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb43c-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cb43c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="cb43c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb43c-115">Element</span></span>|<span data-ttu-id="cb43c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb43c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="cb43c-117">Una colección de elementos de `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="cb43c-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb43c-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb43c-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="cb43c-119">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="cb43c-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
