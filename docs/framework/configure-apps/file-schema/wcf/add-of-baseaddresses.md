---
title: <add> de <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: cd0ef5cc5f0f809bdafa23bd312e7e30fcdccc21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181614"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="0190d-102">\<add> de \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="0190d-102">\<add> of \<baseAddresses></span></span>

<span data-ttu-id="0190d-103">Representa un elemento de configuración que especifica las direcciones base usadas por el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="0190d-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="0190d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0190d-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="0190d-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="0190d-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0190d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0190d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0190d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0190d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0190d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0190d-108">Attributes</span></span>  
  
|<span data-ttu-id="0190d-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0190d-109">Attribute</span></span>|<span data-ttu-id="0190d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0190d-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="0190d-111">Cadena que especifica una dirección base usada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="0190d-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0190d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0190d-112">Child Elements</span></span>  

 <span data-ttu-id="0190d-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0190d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0190d-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0190d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0190d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0190d-115">Element</span></span>|<span data-ttu-id="0190d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0190d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="0190d-117">Una colección de elementos de `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="0190d-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0190d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0190d-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="0190d-119">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="0190d-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
