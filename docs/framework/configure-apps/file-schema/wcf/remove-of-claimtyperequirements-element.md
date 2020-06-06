---
title: <remove>del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399999"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="ecbf3-102">\<remove>del \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="ecbf3-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="ecbf3-103">Especifica los tipos de notificaciones que se van a quitar en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="ecbf3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecbf3-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecbf3-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ecbf3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ecbf3-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecbf3-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ecbf3-107">Attributes</span></span>  
  
|<span data-ttu-id="ecbf3-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ecbf3-108">Attribute</span></span>|<span data-ttu-id="ecbf3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecbf3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ecbf3-110">claimType</span><span class="sxs-lookup"><span data-stu-id="ecbf3-110">claimType</span></span>|<span data-ttu-id="ecbf3-111">URI que define el tipo de una notificación que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecbf3-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ecbf3-112">Child Elements</span></span>  
 <span data-ttu-id="ecbf3-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ecbf3-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ecbf3-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ecbf3-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ecbf3-115">Element</span></span>|<span data-ttu-id="ecbf3-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecbf3-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="ecbf3-117">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="ecbf3-118">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="ecbf3-119">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="ecbf3-120">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="ecbf3-121">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="ecbf3-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ecbf3-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ecbf3-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
