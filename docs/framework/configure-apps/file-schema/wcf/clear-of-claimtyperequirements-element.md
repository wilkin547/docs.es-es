---
title: <clear>del <claimTypeRequirements> elemento
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400529"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="b60db-102">\<borrar > del \<elemento de > claimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="b60db-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="b60db-103">Especifica que se quiten todos los tipos de notificaciones en la credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="b60db-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="b60db-104">Esto asegura que la colección se inicia vacía.</span><span class="sxs-lookup"><span data-stu-id="b60db-104">This ensures that the collection starts empty.</span></span>  
  
<span data-ttu-id="b60db-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b60db-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b60db-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b60db-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b60db-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b60db-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b60db-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b60db-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="b60db-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="b60db-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b60db-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b60db-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="b60db-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de mensajes**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b60db-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="b60db-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequirements**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="b60db-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="b60db-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<borrar >**</span><span class="sxs-lookup"><span data-stu-id="b60db-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60db-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b60db-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b60db-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b60db-115">Attributes and Elements</span></span>  
 <span data-ttu-id="b60db-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b60db-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b60db-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="b60db-117">Attributes</span></span>  
 <span data-ttu-id="b60db-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b60db-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b60db-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b60db-119">Child Elements</span></span>  
 <span data-ttu-id="b60db-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b60db-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b60db-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b60db-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b60db-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b60db-122">Element</span></span>|<span data-ttu-id="b60db-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b60db-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b60db-124">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="b60db-124">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="b60db-125">Especifica una colección de tipos de notificación requeridos.</span><span class="sxs-lookup"><span data-stu-id="b60db-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="b60db-126">Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="b60db-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="b60db-127">En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.</span><span class="sxs-lookup"><span data-stu-id="b60db-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="b60db-128">Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.</span><span class="sxs-lookup"><span data-stu-id="b60db-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="b60db-129">Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.</span><span class="sxs-lookup"><span data-stu-id="b60db-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b60db-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b60db-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
