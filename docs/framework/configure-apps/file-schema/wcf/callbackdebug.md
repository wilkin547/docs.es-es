---
description: 'Más información acerca de: <callbackDebug>'
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 911d738764baa800831c19f4e5d181118d1d3e00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639216"
---
# \<callbackDebug>

<span data-ttu-id="31b42-102">Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="31b42-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**  
  
## <a name="syntax"></a><span data-ttu-id="31b42-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31b42-103">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="31b42-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="31b42-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31b42-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="31b42-105">Attributes and Elements</span></span>  

 <span data-ttu-id="31b42-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="31b42-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31b42-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="31b42-107">Attributes</span></span>  
  
|<span data-ttu-id="31b42-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="31b42-108">Attribute</span></span>|<span data-ttu-id="31b42-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="31b42-109">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="31b42-110">Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.</span><span class="sxs-lookup"><span data-stu-id="31b42-110">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="31b42-111">Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración.</span><span class="sxs-lookup"><span data-stu-id="31b42-111">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="31b42-112">**PRECAUCIÓN:**  Devolver información de excepción administrada a los clientes puede suponer un riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="31b42-112">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="31b42-113">Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.</span><span class="sxs-lookup"><span data-stu-id="31b42-113">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31b42-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="31b42-114">Child Elements</span></span>  

 <span data-ttu-id="31b42-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="31b42-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31b42-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31b42-116">Parent Elements</span></span>  
  
|<span data-ttu-id="31b42-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="31b42-117">Element</span></span>|<span data-ttu-id="31b42-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="31b42-118">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="31b42-119">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="31b42-119">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31b42-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="31b42-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
