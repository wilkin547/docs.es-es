---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e666bac0be772e417f140e1482649f82ea70e2f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673425"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="fba61-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="fba61-101">\<callbackTimeouts></span></span>
<span data-ttu-id="fba61-102">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="fba61-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="fba61-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fba61-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fba61-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="fba61-104">\<behaviors></span></span>  
<span data-ttu-id="fba61-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="fba61-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="fba61-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="fba61-106">\<behavior></span></span>  
<span data-ttu-id="fba61-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="fba61-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fba61-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fba61-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="fba61-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="fba61-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fba61-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fba61-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fba61-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fba61-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fba61-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="fba61-112">Attributes</span></span>  
  
|<span data-ttu-id="fba61-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="fba61-113">Attribute</span></span>|<span data-ttu-id="fba61-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fba61-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="fba61-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fba61-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="fba61-116">El valor predeterminado es "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="fba61-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fba61-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fba61-117">Child Elements</span></span>  
 <span data-ttu-id="fba61-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fba61-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fba61-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fba61-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fba61-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="fba61-120">Element</span></span>|<span data-ttu-id="fba61-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="fba61-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fba61-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fba61-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="fba61-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fba61-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fba61-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fba61-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
