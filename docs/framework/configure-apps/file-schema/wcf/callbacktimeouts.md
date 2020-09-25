---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 98523489aacebf910bcf5d81c479819183887dff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198891"
---
# \<callbackTimeouts>

<span data-ttu-id="357a2-101">Especifica el valor de tiempo de espera cuando fluyen transacciones desde servidor al cliente en un escenario delcontrato de devolución de llamada dúplex.</span><span class="sxs-lookup"><span data-stu-id="357a2-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="357a2-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="357a2-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="357a2-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="357a2-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="357a2-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="357a2-104">Attributes and Elements</span></span>  

 <span data-ttu-id="357a2-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="357a2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="357a2-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="357a2-106">Attributes</span></span>  
  
|<span data-ttu-id="357a2-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="357a2-107">Attribute</span></span>|<span data-ttu-id="357a2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="357a2-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="357a2-109">Un valor <xref:System.TimeSpan> que especifica el intervalo de hora dentro del cual las transacciones deben completarse o finalizarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="357a2-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="357a2-110">El valor predeterminado es "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="357a2-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="357a2-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="357a2-111">Child Elements</span></span>  

 <span data-ttu-id="357a2-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="357a2-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="357a2-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="357a2-113">Parent Elements</span></span>  
  
|<span data-ttu-id="357a2-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="357a2-114">Element</span></span>|<span data-ttu-id="357a2-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="357a2-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="357a2-116">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="357a2-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="357a2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="357a2-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
