---
title: <add> de <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 2c6b5de51e6508965daf6022a47d12d8d73f2a4d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149132"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="c115b-102">\<add> de \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="c115b-102">\<add> of \<defaultPorts></span></span>

<span data-ttu-id="c115b-103">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="c115b-103">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="c115b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c115b-104">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c115b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c115b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c115b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c115b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c115b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c115b-107">Attributes</span></span>  
  
|<span data-ttu-id="c115b-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c115b-108">Attribute</span></span>|<span data-ttu-id="c115b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c115b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c115b-110">port</span><span class="sxs-lookup"><span data-stu-id="c115b-110">port</span></span>|<span data-ttu-id="c115b-111">Entero que especifica el número del puerto de comunicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c115b-111">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="c115b-112">scheme</span><span class="sxs-lookup"><span data-stu-id="c115b-112">scheme</span></span>|<span data-ttu-id="c115b-113">Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="c115b-113">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c115b-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c115b-114">Child Elements</span></span>  

 <span data-ttu-id="c115b-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c115b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c115b-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c115b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c115b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c115b-117">Element</span></span>|<span data-ttu-id="c115b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c115b-118">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="c115b-119">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="c115b-119">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c115b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c115b-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
