---
title: '&lt;callbackDebug&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 93b89787795cb58644b79ae4795e7a036741e138
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="13e29-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="13e29-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="13e29-103">Especifica la depuración de servicio para un objeto de devolución de llamada [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13e29-103">Specifies service debugging for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] callback object.</span></span>  
  
 <span data-ttu-id="13e29-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="13e29-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="13e29-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="13e29-105">\<behaviors></span></span>  
<span data-ttu-id="13e29-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="13e29-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="13e29-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="13e29-107">\<behavior></span></span>  
<span data-ttu-id="13e29-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="13e29-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e29-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13e29-109">Syntax</span></span>  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a><span data-ttu-id="13e29-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="13e29-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13e29-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13e29-111">Attributes and Elements</span></span>  
 <span data-ttu-id="13e29-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13e29-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13e29-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="13e29-113">Attributes</span></span>  
  
|<span data-ttu-id="13e29-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="13e29-114">Attribute</span></span>|<span data-ttu-id="13e29-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="13e29-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="13e29-116">Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.</span><span class="sxs-lookup"><span data-stu-id="13e29-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="13e29-117">Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración.</span><span class="sxs-lookup"><span data-stu-id="13e29-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="13e29-118">**Precaución:** devolver información de excepción administrada a los clientes puede suponer un riesgo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="13e29-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="13e29-119">Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.</span><span class="sxs-lookup"><span data-stu-id="13e29-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13e29-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13e29-120">Child Elements</span></span>  
 <span data-ttu-id="13e29-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="13e29-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13e29-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13e29-122">Parent Elements</span></span>  
  
|<span data-ttu-id="13e29-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="13e29-123">Element</span></span>|<span data-ttu-id="13e29-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="13e29-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13e29-125">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="13e29-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="13e29-126">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="13e29-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13e29-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="13e29-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
