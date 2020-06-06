---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399549"
---
# \<serviceTimeouts>
<span data-ttu-id="63dfc-101">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="63dfc-101">Specifies the timeout for a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**  
  
## <a name="syntax"></a><span data-ttu-id="63dfc-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63dfc-102">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="63dfc-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="63dfc-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63dfc-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63dfc-104">Attributes and Elements</span></span>  
 <span data-ttu-id="63dfc-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="63dfc-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63dfc-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="63dfc-106">Attributes</span></span>  
  
|<span data-ttu-id="63dfc-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="63dfc-107">Attribute</span></span>|<span data-ttu-id="63dfc-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="63dfc-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="63dfc-109">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="63dfc-109">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="63dfc-110">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="63dfc-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63dfc-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63dfc-111">Child Elements</span></span>  
 <span data-ttu-id="63dfc-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="63dfc-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63dfc-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63dfc-113">Parent Elements</span></span>  
  
|<span data-ttu-id="63dfc-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="63dfc-114">Element</span></span>|<span data-ttu-id="63dfc-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="63dfc-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="63dfc-116">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="63dfc-116">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63dfc-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63dfc-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
