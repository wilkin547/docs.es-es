---
title: <add> de <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850310"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="d401d-102">\<Agregar > de \<transportConfigurationType ></span><span class="sxs-lookup"><span data-stu-id="d401d-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="d401d-103">Este elemento es una par clave-valor, que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="d401d-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
<span data-ttu-id="d401d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d401d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d401d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d401d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d401d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceHostingEnvironment**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="d401d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="d401d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> transportConfigurationTypes**](transportconfigurationtypes.md)</span><span class="sxs-lookup"><span data-stu-id="d401d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)</span></span>\
<span data-ttu-id="d401d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="d401d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d401d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d401d-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d401d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d401d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d401d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d401d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d401d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d401d-112">Attributes</span></span>  
  
|<span data-ttu-id="d401d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d401d-113">Attribute</span></span>|<span data-ttu-id="d401d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d401d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d401d-115">name</span><span class="sxs-lookup"><span data-stu-id="d401d-115">name</span></span>|<span data-ttu-id="d401d-116">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="d401d-116">Required String attribute.</span></span><br /><br /> <span data-ttu-id="d401d-117">Contiene una clave definida por el usuario que identifica de forma única el tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="d401d-117">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="d401d-118">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="d401d-118">transportConfigurationType</span></span>|<span data-ttu-id="d401d-119">Una cadena que contiene el tipo que implementa el transporte concreto.</span><span class="sxs-lookup"><span data-stu-id="d401d-119">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d401d-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d401d-120">Child Elements</span></span>  
 <span data-ttu-id="d401d-121">None</span><span class="sxs-lookup"><span data-stu-id="d401d-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d401d-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d401d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d401d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d401d-123">Element</span></span>|<span data-ttu-id="d401d-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d401d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d401d-125">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="d401d-125">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="d401d-126">Una colección de tipos que implementan el transporte concreto.</span><span class="sxs-lookup"><span data-stu-id="d401d-126">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d401d-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d401d-127">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="d401d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d401d-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="d401d-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d401d-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
