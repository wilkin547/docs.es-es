---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398405"
---
# <a name="allowaccounts"></a><span data-ttu-id="47220-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="47220-101">\<allowAccounts></span></span>
<span data-ttu-id="47220-102">Contiene una colección de elementos de configuración que especifican las cuentas de usuario para los procesos que hospedan servicios Windows Communication Foundation (WCF) y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="47220-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="47220-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="47220-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="47220-104">&nbsp;&nbsp;[ **\<System. serviceModel. Activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="47220-104">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="47220-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> net. Pipe**](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="47220-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="47220-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> allowAccounts**</span><span class="sxs-lookup"><span data-stu-id="47220-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47220-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47220-107">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47220-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="47220-108">Attributes and Elements</span></span>  
 <span data-ttu-id="47220-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="47220-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47220-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="47220-110">Attributes</span></span>  
 <span data-ttu-id="47220-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="47220-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="47220-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="47220-112">Child Elements</span></span>  
  
|<span data-ttu-id="47220-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="47220-113">Attribute</span></span>|<span data-ttu-id="47220-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="47220-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="47220-115">\<add></span><span class="sxs-lookup"><span data-stu-id="47220-115">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="47220-116">Agrega una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="47220-116">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47220-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="47220-117">Parent Elements</span></span>  
  
|<span data-ttu-id="47220-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="47220-118">Element</span></span>|<span data-ttu-id="47220-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="47220-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47220-120">net. Pipe > o [ \<](net-pipe.md) [ \<net. TCP >](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="47220-120">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="47220-121">Especifica la configuración para la Canalización de Red o servicios de uso compartido de TCP.</span><span class="sxs-lookup"><span data-stu-id="47220-121">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47220-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="47220-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
