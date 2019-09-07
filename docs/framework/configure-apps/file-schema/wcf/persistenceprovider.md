---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400075"
---
# <a name="persistenceprovider"></a><span data-ttu-id="8c8d3-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="8c8d3-101">\<persistenceProvider></span></span>
<span data-ttu-id="8c8d3-102">Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="8c8d3-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
<span data-ttu-id="8c8d3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c8d3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8c8d3-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8c8d3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8c8d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8c8d3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="8c8d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8c8d3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="8c8d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8c8d3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="8c8d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de persistenceProvider**</span><span class="sxs-lookup"><span data-stu-id="8c8d3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c8d3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c8d3-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c8d3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8c8d3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8c8d3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8c8d3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c8d3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8c8d3-112">Attributes</span></span>  
  
|<span data-ttu-id="8c8d3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8c8d3-113">Attribute</span></span>|<span data-ttu-id="8c8d3-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8c8d3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c8d3-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="8c8d3-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="8c8d3-116">Un valor <xref:System.TimeSpan> que especifica el tiempo de espera usado en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="8c8d3-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="8c8d3-117">El valor predeterminado es "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="8c8d3-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="8c8d3-118">type</span><span class="sxs-lookup"><span data-stu-id="8c8d3-118">type</span></span>|<span data-ttu-id="8c8d3-119">Una cadena que especifica el tipo del generador del proveedor de persistencia que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="8c8d3-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c8d3-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8c8d3-120">Child Elements</span></span>  
 <span data-ttu-id="8c8d3-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8c8d3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c8d3-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8c8d3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8c8d3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c8d3-123">Element</span></span>|<span data-ttu-id="8c8d3-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8c8d3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c8d3-125">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="8c8d3-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8c8d3-126">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8c8d3-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c8d3-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c8d3-127">Remarks</span></span>  
 <span data-ttu-id="8c8d3-128">Este elemento especifica el proveedor de persistencia que se va a utilizar para serializar el estado de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="8c8d3-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="8c8d3-129">Se debería utilizar junto con `wsHttpContextBinding` que pasa la información de estado en encabezados HTTP.</span><span class="sxs-lookup"><span data-stu-id="8c8d3-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8d3-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c8d3-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
