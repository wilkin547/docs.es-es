---
description: 'Más información sobre: <clear> del <claimTypeRequirements> elemento'
title: <clear> del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: d25dad5afcec352f040ea4f8c08e5ffa2bc16d19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638891"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="0bd02-103">\<clear> del \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="0bd02-103">\<clear> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="0bd02-104">Especifica que se quiten todos los tipos de notificaciones en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="0bd02-104">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="0bd02-105">Esto asegura que la colección se inicia vacía.</span><span class="sxs-lookup"><span data-stu-id="0bd02-105">This ensures that the collection starts empty.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="0bd02-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bd02-106">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bd02-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0bd02-107">Attributes and Elements</span></span>  

 <span data-ttu-id="0bd02-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0bd02-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bd02-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0bd02-109">Attributes</span></span>  

 <span data-ttu-id="0bd02-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0bd02-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0bd02-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0bd02-111">Child Elements</span></span>  

 <span data-ttu-id="0bd02-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0bd02-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bd02-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0bd02-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0bd02-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="0bd02-114">Element</span></span>|<span data-ttu-id="0bd02-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bd02-115">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="0bd02-116">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="0bd02-116">Specifies a collection of required claim types.</span></span> <span data-ttu-id="0bd02-117">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="0bd02-117">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="0bd02-118">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="0bd02-118">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="0bd02-119">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="0bd02-119">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="0bd02-120">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="0bd02-120">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0bd02-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bd02-121">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
