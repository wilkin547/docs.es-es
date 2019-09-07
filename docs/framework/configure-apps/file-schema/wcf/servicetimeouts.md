---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399549"
---
# <a name="servicetimeouts"></a><span data-ttu-id="99a7f-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="99a7f-101">\<serviceTimeouts></span></span>
<span data-ttu-id="99a7f-102">Especifica el tiempo de espera para un servicio.</span><span class="sxs-lookup"><span data-stu-id="99a7f-102">Specifies the timeout for a service.</span></span>  
  
<span data-ttu-id="99a7f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99a7f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99a7f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="99a7f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="99a7f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99a7f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="99a7f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99a7f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="99a7f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="99a7f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="99a7f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceTimeouts**</span><span class="sxs-lookup"><span data-stu-id="99a7f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99a7f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99a7f-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="99a7f-110">Type</span><span class="sxs-lookup"><span data-stu-id="99a7f-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99a7f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99a7f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99a7f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99a7f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99a7f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="99a7f-113">Attributes</span></span>  
  
|<span data-ttu-id="99a7f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="99a7f-114">Attribute</span></span>|<span data-ttu-id="99a7f-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="99a7f-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="99a7f-116">Valor <xref:System.TimeSpan> que especifica el intervalo de tiempo que una transacción debe fluir del cliente al servidor.</span><span class="sxs-lookup"><span data-stu-id="99a7f-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="99a7f-117">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="99a7f-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99a7f-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99a7f-118">Child Elements</span></span>  
 <span data-ttu-id="99a7f-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99a7f-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99a7f-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99a7f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="99a7f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="99a7f-121">Element</span></span>|<span data-ttu-id="99a7f-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="99a7f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99a7f-123">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="99a7f-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="99a7f-124">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="99a7f-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99a7f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="99a7f-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
