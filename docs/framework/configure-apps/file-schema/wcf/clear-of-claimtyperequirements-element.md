---
title: <clear>del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400529"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="600de-102">\<clear>del \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="600de-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="600de-103">Especifica que se quiten todos los tipos de notificaciones en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="600de-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="600de-104">Esto asegura que la colección se inicia vacía.</span><span class="sxs-lookup"><span data-stu-id="600de-104">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="600de-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="600de-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="600de-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="600de-106">Attributes and Elements</span></span>  
 <span data-ttu-id="600de-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="600de-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="600de-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="600de-108">Attributes</span></span>  
 <span data-ttu-id="600de-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="600de-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="600de-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="600de-110">Child Elements</span></span>  
 <span data-ttu-id="600de-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="600de-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="600de-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="600de-112">Parent Elements</span></span>  
  
|<span data-ttu-id="600de-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="600de-113">Element</span></span>|<span data-ttu-id="600de-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="600de-114">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="600de-115">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="600de-115">Specifies a collection of required claim types.</span></span> <span data-ttu-id="600de-116">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="600de-116">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="600de-117">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="600de-117">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="600de-118">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="600de-118">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="600de-119">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="600de-119">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="600de-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="600de-120">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
