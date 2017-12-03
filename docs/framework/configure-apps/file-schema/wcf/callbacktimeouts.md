---
title: '&lt;callbackTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5a030a615aae0159e1426bdf4c640ddfab7287dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="f0cc3-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="f0cc3-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="f0cc3-103">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="f0cc3-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="f0cc3-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f0cc3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f0cc3-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="f0cc3-105">\<behaviors></span></span>  
<span data-ttu-id="f0cc3-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f0cc3-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f0cc3-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f0cc3-107">\<behavior></span></span>  
<span data-ttu-id="f0cc3-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="f0cc3-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0cc3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0cc3-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="f0cc3-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="f0cc3-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0cc3-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f0cc3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f0cc3-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f0cc3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0cc3-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f0cc3-113">Attributes</span></span>  
  
|<span data-ttu-id="f0cc3-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f0cc3-114">Attribute</span></span>|<span data-ttu-id="f0cc3-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0cc3-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="f0cc3-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f0cc3-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="f0cc3-117">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="f0cc3-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0cc3-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f0cc3-118">Child Elements</span></span>  
 <span data-ttu-id="f0cc3-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f0cc3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0cc3-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0cc3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f0cc3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0cc3-121">Element</span></span>|<span data-ttu-id="f0cc3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0cc3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0cc3-123">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f0cc3-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f0cc3-124">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f0cc3-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0cc3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0cc3-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
