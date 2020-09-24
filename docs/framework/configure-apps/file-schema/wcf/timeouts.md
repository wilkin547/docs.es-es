---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: f7e513bb5c486fa5f7c39c9b2e3cfcd26bd7c219
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157101"
---
# \<timeOuts>

<span data-ttu-id="d9153-101">Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="d9153-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="d9153-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9153-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9153-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9153-103">Attributes and Elements</span></span>  

 <span data-ttu-id="d9153-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9153-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9153-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9153-105">Attributes</span></span>  
  
|<span data-ttu-id="d9153-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="d9153-106">Attribute</span></span>|<span data-ttu-id="d9153-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9153-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="d9153-108">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.</span><span class="sxs-lookup"><span data-stu-id="d9153-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="d9153-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.</span><span class="sxs-lookup"><span data-stu-id="d9153-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9153-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9153-110">Child Elements</span></span>  

 <span data-ttu-id="d9153-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d9153-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9153-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9153-112">Parent Elements</span></span>  
  
|<span data-ttu-id="d9153-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9153-113">Element</span></span>|<span data-ttu-id="d9153-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9153-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="d9153-115">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="d9153-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9153-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9153-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="d9153-117">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d9153-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
