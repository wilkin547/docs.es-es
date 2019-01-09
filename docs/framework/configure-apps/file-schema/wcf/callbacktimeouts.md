---
title: '&lt;callbackTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 85e7b1f0d009e27cbacd9f69b381e4f05984bf56
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149116"
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="95ed9-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="95ed9-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="95ed9-103">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="95ed9-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="95ed9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="95ed9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="95ed9-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="95ed9-105">\<behaviors></span></span>  
<span data-ttu-id="95ed9-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="95ed9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="95ed9-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="95ed9-107">\<behavior></span></span>  
<span data-ttu-id="95ed9-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="95ed9-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ed9-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95ed9-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="95ed9-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="95ed9-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95ed9-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95ed9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="95ed9-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95ed9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95ed9-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="95ed9-113">Attributes</span></span>  
  
|<span data-ttu-id="95ed9-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="95ed9-114">Attribute</span></span>|<span data-ttu-id="95ed9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="95ed9-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="95ed9-116">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="95ed9-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="95ed9-117">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="95ed9-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95ed9-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95ed9-118">Child Elements</span></span>  
 <span data-ttu-id="95ed9-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="95ed9-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95ed9-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95ed9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="95ed9-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="95ed9-121">Element</span></span>|<span data-ttu-id="95ed9-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="95ed9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95ed9-123">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="95ed9-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="95ed9-124">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="95ed9-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95ed9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="95ed9-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
