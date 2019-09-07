---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398184"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="33e0d-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="33e0d-101">\<callbackTimeouts></span></span>
<span data-ttu-id="33e0d-102">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="33e0d-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
<span data-ttu-id="33e0d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33e0d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33e0d-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="33e0d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33e0d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33e0d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="33e0d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33e0d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="33e0d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="33e0d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="33e0d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> callbackTimeOuts**</span><span class="sxs-lookup"><span data-stu-id="33e0d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e0d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33e0d-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="33e0d-110">Type</span><span class="sxs-lookup"><span data-stu-id="33e0d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33e0d-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="33e0d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="33e0d-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="33e0d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33e0d-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="33e0d-113">Attributes</span></span>  
  
|<span data-ttu-id="33e0d-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="33e0d-114">Attribute</span></span>|<span data-ttu-id="33e0d-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33e0d-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="33e0d-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="33e0d-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="33e0d-117">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="33e0d-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33e0d-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="33e0d-118">Child Elements</span></span>  
 <span data-ttu-id="33e0d-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="33e0d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33e0d-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="33e0d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="33e0d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="33e0d-121">Element</span></span>|<span data-ttu-id="33e0d-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33e0d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33e0d-123">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="33e0d-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="33e0d-124">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="33e0d-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33e0d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="33e0d-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
