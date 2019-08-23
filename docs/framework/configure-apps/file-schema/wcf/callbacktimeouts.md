---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: d57a888a19e684ac13632c1ab2476e304667c3e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919666"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="35a5d-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="35a5d-101">\<callbackTimeouts></span></span>
<span data-ttu-id="35a5d-102">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="35a5d-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="35a5d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="35a5d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="35a5d-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="35a5d-104">\<behaviors></span></span>  
<span data-ttu-id="35a5d-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="35a5d-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="35a5d-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="35a5d-106">\<behavior></span></span>  
<span data-ttu-id="35a5d-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="35a5d-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a5d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35a5d-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="35a5d-109">Type</span><span class="sxs-lookup"><span data-stu-id="35a5d-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35a5d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="35a5d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35a5d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="35a5d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35a5d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="35a5d-112">Attributes</span></span>  
  
|<span data-ttu-id="35a5d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="35a5d-113">Attribute</span></span>|<span data-ttu-id="35a5d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="35a5d-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="35a5d-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="35a5d-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="35a5d-116">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="35a5d-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35a5d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="35a5d-117">Child Elements</span></span>  
 <span data-ttu-id="35a5d-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="35a5d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35a5d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="35a5d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="35a5d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="35a5d-120">Element</span></span>|<span data-ttu-id="35a5d-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="35a5d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35a5d-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="35a5d-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="35a5d-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="35a5d-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35a5d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="35a5d-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
