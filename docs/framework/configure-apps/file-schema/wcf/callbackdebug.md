---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 1aa292a3fe06af9cf1dbc53ebf5bbdf9841be8d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687380"
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="aca16-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="aca16-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="aca16-103">Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="aca16-103">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="aca16-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="aca16-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="aca16-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="aca16-105">\<behaviors></span></span>  
<span data-ttu-id="aca16-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="aca16-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="aca16-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="aca16-107">\<behavior></span></span>  
<span data-ttu-id="aca16-108">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="aca16-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aca16-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aca16-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="aca16-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="aca16-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aca16-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aca16-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aca16-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aca16-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aca16-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="aca16-113">Attributes</span></span>  
  
|<span data-ttu-id="aca16-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="aca16-114">Attribute</span></span>|<span data-ttu-id="aca16-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca16-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="aca16-116">Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.</span><span class="sxs-lookup"><span data-stu-id="aca16-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="aca16-117">Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración.</span><span class="sxs-lookup"><span data-stu-id="aca16-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="aca16-118">**Advertencia:**  Devolver información de excepción administrada a los clientes puede ser un riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="aca16-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="aca16-119">Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.</span><span class="sxs-lookup"><span data-stu-id="aca16-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aca16-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aca16-120">Child Elements</span></span>  
 <span data-ttu-id="aca16-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="aca16-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aca16-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aca16-122">Parent Elements</span></span>  
  
|<span data-ttu-id="aca16-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="aca16-123">Element</span></span>|<span data-ttu-id="aca16-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="aca16-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aca16-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="aca16-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="aca16-126">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="aca16-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aca16-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="aca16-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
