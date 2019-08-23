---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 91e7bd63bf496f2c38776d88173ed2ac12a3b888
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926318"
---
# <a name="callbackdebug"></a><span data-ttu-id="9eb6a-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="9eb6a-101">\<callbackDebug></span></span>
<span data-ttu-id="9eb6a-102">Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9eb6a-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="9eb6a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9eb6a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9eb6a-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9eb6a-104">\<behaviors></span></span>  
<span data-ttu-id="9eb6a-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9eb6a-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="9eb6a-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9eb6a-106">\<behavior></span></span>  
<span data-ttu-id="9eb6a-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="9eb6a-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb6a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9eb6a-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="9eb6a-109">Type</span><span class="sxs-lookup"><span data-stu-id="9eb6a-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9eb6a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9eb6a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9eb6a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9eb6a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9eb6a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9eb6a-112">Attributes</span></span>  
  
|<span data-ttu-id="9eb6a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9eb6a-113">Attribute</span></span>|<span data-ttu-id="9eb6a-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9eb6a-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="9eb6a-115">Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.</span><span class="sxs-lookup"><span data-stu-id="9eb6a-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="9eb6a-116">Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración.</span><span class="sxs-lookup"><span data-stu-id="9eb6a-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="9eb6a-117">**Advertencia:**  Devolver información de excepción administrada a los clientes puede ser un riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="9eb6a-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="9eb6a-118">Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.</span><span class="sxs-lookup"><span data-stu-id="9eb6a-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9eb6a-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9eb6a-119">Child Elements</span></span>  
 <span data-ttu-id="9eb6a-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9eb6a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9eb6a-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9eb6a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9eb6a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9eb6a-122">Element</span></span>|<span data-ttu-id="9eb6a-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9eb6a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9eb6a-124">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9eb6a-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9eb6a-125">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9eb6a-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9eb6a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9eb6a-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
