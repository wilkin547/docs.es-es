---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: a1190eb1c015ba07488ff5a5952f2f5f1b10974c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152274"
---
# <a name="callbackdebug"></a><span data-ttu-id="77d23-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="77d23-101">\<callbackDebug></span></span>
<span data-ttu-id="77d23-102">Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="77d23-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="77d23-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="77d23-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="77d23-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="77d23-104">\<behaviors></span></span>  
<span data-ttu-id="77d23-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="77d23-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="77d23-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="77d23-106">\<behavior></span></span>  
<span data-ttu-id="77d23-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="77d23-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77d23-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77d23-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="77d23-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="77d23-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77d23-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="77d23-110">Attributes and Elements</span></span>  
 <span data-ttu-id="77d23-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="77d23-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77d23-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="77d23-112">Attributes</span></span>  
  
|<span data-ttu-id="77d23-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="77d23-113">Attribute</span></span>|<span data-ttu-id="77d23-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="77d23-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="77d23-115">Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.</span><span class="sxs-lookup"><span data-stu-id="77d23-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="77d23-116">Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración.</span><span class="sxs-lookup"><span data-stu-id="77d23-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="77d23-117">**Advertencia:**  Devolver información de excepción administrada a los clientes puede ser un riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="77d23-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="77d23-118">Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.</span><span class="sxs-lookup"><span data-stu-id="77d23-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77d23-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="77d23-119">Child Elements</span></span>  
 <span data-ttu-id="77d23-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="77d23-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77d23-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="77d23-121">Parent Elements</span></span>  
  
|<span data-ttu-id="77d23-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="77d23-122">Element</span></span>|<span data-ttu-id="77d23-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="77d23-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77d23-124">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="77d23-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="77d23-125">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="77d23-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77d23-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="77d23-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
