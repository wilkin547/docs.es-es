---
description: 'Más información sobre: <remove> del <claimTypeRequirements> elemento'
title: <remove> del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 2ec917d27966954382e5b091fd538168b48b5ffb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786907"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="85313-103">\<remove> del \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="85313-103">\<remove> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="85313-104">Especifica los tipos de notificaciones que se van a quitar en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="85313-104">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="85313-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85313-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85313-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85313-106">Attributes and Elements</span></span>  

 <span data-ttu-id="85313-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85313-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85313-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="85313-108">Attributes</span></span>  
  
|<span data-ttu-id="85313-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="85313-109">Attribute</span></span>|<span data-ttu-id="85313-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="85313-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85313-111">claimType</span><span class="sxs-lookup"><span data-stu-id="85313-111">claimType</span></span>|<span data-ttu-id="85313-112">URI que define el tipo de una notificación que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="85313-112">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85313-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85313-113">Child Elements</span></span>  

 <span data-ttu-id="85313-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85313-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85313-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85313-115">Parent Elements</span></span>  
  
|<span data-ttu-id="85313-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="85313-116">Element</span></span>|<span data-ttu-id="85313-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="85313-117">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="85313-118">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="85313-118">Specifies a collection of required claim types.</span></span> <span data-ttu-id="85313-119">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="85313-119">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="85313-120">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="85313-120">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="85313-121">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="85313-121">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="85313-122">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="85313-122">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85313-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="85313-123">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
