---
description: 'Más información acerca de: <timeOuts>'
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 097569d1742f6486ddfb5fb3c3d98ba106424f45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786595"
---
# \<timeOuts>

<span data-ttu-id="85e49-102">Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="85e49-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="85e49-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85e49-103">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85e49-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85e49-104">Attributes and Elements</span></span>  

 <span data-ttu-id="85e49-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85e49-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85e49-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="85e49-106">Attributes</span></span>  
  
|<span data-ttu-id="85e49-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="85e49-107">Attribute</span></span>|<span data-ttu-id="85e49-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="85e49-108">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="85e49-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.</span><span class="sxs-lookup"><span data-stu-id="85e49-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="85e49-110">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.</span><span class="sxs-lookup"><span data-stu-id="85e49-110">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85e49-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85e49-111">Child Elements</span></span>  

 <span data-ttu-id="85e49-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85e49-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85e49-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85e49-113">Parent Elements</span></span>  
  
|<span data-ttu-id="85e49-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="85e49-114">Element</span></span>|<span data-ttu-id="85e49-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="85e49-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="85e49-116">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="85e49-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85e49-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="85e49-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="85e49-118">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="85e49-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
