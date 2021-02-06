---
description: 'Más información acerca de: <clientVia>'
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 651af0c310504f7672ca172d7df609365c319506
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638779"
---
# \<clientVia>

<span data-ttu-id="9cb0f-102">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="9cb0f-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="9cb0f-103">Para obtener más información, vea <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="9cb0f-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="9cb0f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cb0f-104">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cb0f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9cb0f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9cb0f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9cb0f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cb0f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="9cb0f-107">Attributes</span></span>  
  
|<span data-ttu-id="9cb0f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="9cb0f-108">Attribute</span></span>|<span data-ttu-id="9cb0f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cb0f-109">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="9cb0f-110">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="9cb0f-110">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cb0f-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9cb0f-111">Child Elements</span></span>  

 <span data-ttu-id="9cb0f-112">None</span><span class="sxs-lookup"><span data-stu-id="9cb0f-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9cb0f-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9cb0f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="9cb0f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9cb0f-114">Element</span></span>|<span data-ttu-id="9cb0f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cb0f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9cb0f-116">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9cb0f-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cb0f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cb0f-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
