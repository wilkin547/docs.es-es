---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398107"
---
# \<clientVia>
<span data-ttu-id="6b94d-101">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="6b94d-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="6b94d-102">Para obtener más información, vea <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="6b94d-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="6b94d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b94d-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b94d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6b94d-104">Attributes and Elements</span></span>  
 <span data-ttu-id="6b94d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6b94d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b94d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="6b94d-106">Attributes</span></span>  
  
|<span data-ttu-id="6b94d-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="6b94d-107">Attribute</span></span>|<span data-ttu-id="6b94d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b94d-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="6b94d-109">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="6b94d-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b94d-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6b94d-110">Child Elements</span></span>  
 <span data-ttu-id="6b94d-111">None</span><span class="sxs-lookup"><span data-stu-id="6b94d-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b94d-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6b94d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="6b94d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b94d-113">Element</span></span>|<span data-ttu-id="6b94d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b94d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6b94d-115">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6b94d-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b94d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b94d-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
