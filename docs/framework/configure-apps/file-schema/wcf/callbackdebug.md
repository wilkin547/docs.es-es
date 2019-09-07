---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 92a8fa83b5cf5f429278ac8edc8439b627839aad
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400570"
---
# <a name="callbackdebug"></a><span data-ttu-id="f857f-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="f857f-101">\<callbackDebug></span></span>
<span data-ttu-id="f857f-102">Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f857f-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
<span data-ttu-id="f857f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f857f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f857f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f857f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f857f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f857f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f857f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f857f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="f857f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f857f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="f857f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> callbackDebug**</span><span class="sxs-lookup"><span data-stu-id="f857f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f857f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f857f-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="f857f-110">Type</span><span class="sxs-lookup"><span data-stu-id="f857f-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f857f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f857f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f857f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f857f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f857f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f857f-113">Attributes</span></span>  
  
|<span data-ttu-id="f857f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f857f-114">Attribute</span></span>|<span data-ttu-id="f857f-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f857f-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="f857f-116">Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.</span><span class="sxs-lookup"><span data-stu-id="f857f-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="f857f-117">Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración.</span><span class="sxs-lookup"><span data-stu-id="f857f-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="f857f-118">**Advertencia:**  Devolver información de excepción administrada a los clientes puede ser un riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="f857f-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="f857f-119">Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.</span><span class="sxs-lookup"><span data-stu-id="f857f-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f857f-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f857f-120">Child Elements</span></span>  
 <span data-ttu-id="f857f-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f857f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f857f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f857f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f857f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="f857f-123">Element</span></span>|<span data-ttu-id="f857f-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f857f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f857f-125">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f857f-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f857f-126">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f857f-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f857f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f857f-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
