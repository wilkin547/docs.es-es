---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399708"
---
# \<serviceAuthenticationManager>
<span data-ttu-id="4a16d-101">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, un mensaje o un autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="4a16d-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="4a16d-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a16d-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a16d-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4a16d-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4a16d-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4a16d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a16d-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="4a16d-105">Attributes</span></span>  
  
|<span data-ttu-id="4a16d-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="4a16d-106">Attribute</span></span>|<span data-ttu-id="4a16d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a16d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a16d-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="4a16d-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="4a16d-109">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="4a16d-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a16d-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4a16d-110">Child Elements</span></span>  
 <span data-ttu-id="4a16d-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4a16d-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a16d-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4a16d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="4a16d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a16d-113">Element</span></span>|<span data-ttu-id="4a16d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a16d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4a16d-115">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="4a16d-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a16d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a16d-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
