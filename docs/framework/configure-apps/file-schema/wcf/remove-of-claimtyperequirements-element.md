---
title: <remove> del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 773f37156969f64f02711e6a60764aeb7e50a840
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181328"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="e54dd-102">\<remove> del \<claimTypeRequirements> elemento</span><span class="sxs-lookup"><span data-stu-id="e54dd-102">\<remove> of \<claimTypeRequirements> element</span></span>

<span data-ttu-id="e54dd-103">Especifica los tipos de notificaciones que se van a quitar en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="e54dd-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="e54dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e54dd-104">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e54dd-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e54dd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e54dd-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e54dd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e54dd-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e54dd-107">Attributes</span></span>  
  
|<span data-ttu-id="e54dd-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e54dd-108">Attribute</span></span>|<span data-ttu-id="e54dd-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e54dd-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e54dd-110">claimType</span><span class="sxs-lookup"><span data-stu-id="e54dd-110">claimType</span></span>|<span data-ttu-id="e54dd-111">URI que define el tipo de una notificación que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="e54dd-111">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e54dd-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e54dd-112">Child Elements</span></span>  

 <span data-ttu-id="e54dd-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e54dd-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e54dd-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e54dd-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e54dd-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e54dd-115">Element</span></span>|<span data-ttu-id="e54dd-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e54dd-116">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="e54dd-117">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="e54dd-117">Specifies a collection of required claim types.</span></span> <span data-ttu-id="e54dd-118">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="e54dd-118">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="e54dd-119">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="e54dd-119">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="e54dd-120">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="e54dd-120">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="e54dd-121">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="e54dd-121">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e54dd-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e54dd-122">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
