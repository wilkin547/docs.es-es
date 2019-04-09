---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e666bac0be772e417f140e1482649f82ea70e2f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173646"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="52829-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="52829-101">\<callbackTimeouts></span></span>
<span data-ttu-id="52829-102">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="52829-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="52829-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="52829-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="52829-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="52829-104">\<behaviors></span></span>  
<span data-ttu-id="52829-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="52829-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="52829-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="52829-106">\<behavior></span></span>  
<span data-ttu-id="52829-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="52829-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52829-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52829-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="52829-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="52829-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52829-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="52829-110">Attributes and Elements</span></span>  
 <span data-ttu-id="52829-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="52829-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52829-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="52829-112">Attributes</span></span>  
  
|<span data-ttu-id="52829-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="52829-113">Attribute</span></span>|<span data-ttu-id="52829-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="52829-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="52829-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="52829-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="52829-116">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="52829-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52829-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="52829-117">Child Elements</span></span>  
 <span data-ttu-id="52829-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="52829-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52829-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="52829-119">Parent Elements</span></span>  
  
|<span data-ttu-id="52829-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="52829-120">Element</span></span>|<span data-ttu-id="52829-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="52829-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52829-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="52829-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="52829-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="52829-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52829-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="52829-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
