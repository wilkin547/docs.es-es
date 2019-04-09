---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dc8dea0ddd1ea074c08952e3e2ebfef2d12f7183
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099292"
---
# <a name="persistenceprovider"></a><span data-ttu-id="1adc2-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="1adc2-101">\<persistenceProvider></span></span>
<span data-ttu-id="1adc2-102">Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="1adc2-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="1adc2-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1adc2-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1adc2-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="1adc2-104">\<behaviors></span></span>  
<span data-ttu-id="1adc2-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1adc2-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="1adc2-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="1adc2-106">\<behavior></span></span>  
<span data-ttu-id="1adc2-107">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="1adc2-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1adc2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1adc2-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1adc2-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1adc2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1adc2-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1adc2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1adc2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="1adc2-111">Attributes</span></span>  
  
|<span data-ttu-id="1adc2-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="1adc2-112">Attribute</span></span>|<span data-ttu-id="1adc2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1adc2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1adc2-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="1adc2-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="1adc2-115">Un valor <xref:System.TimeSpan> que especifica el tiempo de espera usado en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="1adc2-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="1adc2-116">El valor predeterminado es "00: 00:30".</span><span class="sxs-lookup"><span data-stu-id="1adc2-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="1adc2-117">type</span><span class="sxs-lookup"><span data-stu-id="1adc2-117">type</span></span>|<span data-ttu-id="1adc2-118">Una cadena que especifica el tipo del generador del proveedor de persistencia que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="1adc2-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1adc2-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1adc2-119">Child Elements</span></span>  
 <span data-ttu-id="1adc2-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1adc2-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1adc2-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1adc2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1adc2-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="1adc2-122">Element</span></span>|<span data-ttu-id="1adc2-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="1adc2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1adc2-124">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="1adc2-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1adc2-125">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1adc2-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1adc2-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1adc2-126">Remarks</span></span>  
 <span data-ttu-id="1adc2-127">Este elemento especifica el proveedor de persistencia que se va a utilizar para serializar el estado de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="1adc2-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="1adc2-128">Se debería utilizar junto con `wsHttpContextBinding` que pasa la información de estado en encabezados HTTP.</span><span class="sxs-lookup"><span data-stu-id="1adc2-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1adc2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="1adc2-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
