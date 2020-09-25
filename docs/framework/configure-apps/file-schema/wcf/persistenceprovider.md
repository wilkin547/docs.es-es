---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dbf0ba565d4e3e2d65b4a81eb5d345fa90fb43c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181432"
---
# \<persistenceProvider>

<span data-ttu-id="66df6-101">Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="66df6-101">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="66df6-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66df6-102">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66df6-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="66df6-103">Attributes and Elements</span></span>  

 <span data-ttu-id="66df6-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="66df6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66df6-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="66df6-105">Attributes</span></span>  
  
|<span data-ttu-id="66df6-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="66df6-106">Attribute</span></span>|<span data-ttu-id="66df6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="66df6-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66df6-108">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="66df6-108">persistenceOperationTimeout</span></span>|<span data-ttu-id="66df6-109">Un valor <xref:System.TimeSpan> que especifica el tiempo de espera usado en las operaciones de persistencia.</span><span class="sxs-lookup"><span data-stu-id="66df6-109">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="66df6-110">El valor predeterminado es "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="66df6-110">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="66df6-111">type</span><span class="sxs-lookup"><span data-stu-id="66df6-111">type</span></span>|<span data-ttu-id="66df6-112">Una cadena que especifica el tipo del generador del proveedor de persistencia que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="66df6-112">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66df6-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="66df6-113">Child Elements</span></span>  

 <span data-ttu-id="66df6-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="66df6-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="66df6-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="66df6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="66df6-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="66df6-116">Element</span></span>|<span data-ttu-id="66df6-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="66df6-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="66df6-118">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="66df6-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66df6-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="66df6-119">Remarks</span></span>  

 <span data-ttu-id="66df6-120">Este elemento especifica el proveedor de persistencia que se va a utilizar para serializar el estado de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="66df6-120">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="66df6-121">Se debería utilizar junto con `wsHttpContextBinding` que pasa la información de estado en encabezados HTTP.</span><span class="sxs-lookup"><span data-stu-id="66df6-121">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66df6-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66df6-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
