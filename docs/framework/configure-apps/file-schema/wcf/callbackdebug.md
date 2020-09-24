---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 02632cc3f668bb9e4cc6f8c9726d7bcb3cab2c5d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183824"
---
# \<callbackDebug>

<span data-ttu-id="0bfac-101">Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0bfac-101">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**  
  
## <a name="syntax"></a><span data-ttu-id="0bfac-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bfac-102">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="0bfac-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="0bfac-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bfac-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0bfac-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0bfac-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0bfac-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bfac-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="0bfac-106">Attributes</span></span>  
  
|<span data-ttu-id="0bfac-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="0bfac-107">Attribute</span></span>|<span data-ttu-id="0bfac-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bfac-108">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="0bfac-109">Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.</span><span class="sxs-lookup"><span data-stu-id="0bfac-109">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="0bfac-110">Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración.</span><span class="sxs-lookup"><span data-stu-id="0bfac-110">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="0bfac-111">**PRECAUCIÓN:**  Devolver información de excepción administrada a los clientes puede suponer un riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0bfac-111">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="0bfac-112">Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.</span><span class="sxs-lookup"><span data-stu-id="0bfac-112">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bfac-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0bfac-113">Child Elements</span></span>  

 <span data-ttu-id="0bfac-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0bfac-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bfac-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0bfac-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0bfac-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0bfac-116">Element</span></span>|<span data-ttu-id="0bfac-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bfac-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0bfac-118">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0bfac-118">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bfac-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0bfac-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
