---
description: 'Más información sobre: <add> de <transportConfigurationType>'
title: <add> de <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 4a4a68e1f70bcb2ec7d55d5d6c3b530e71ddc55d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750018"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="02a04-103">\<add> de \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="02a04-103">\<add> of \<transportConfigurationType></span></span>

<span data-ttu-id="02a04-104">Este elemento es una par clave-valor, que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="02a04-104">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="02a04-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02a04-105">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02a04-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02a04-106">Attributes and Elements</span></span>  

 <span data-ttu-id="02a04-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02a04-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02a04-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="02a04-108">Attributes</span></span>  
  
|<span data-ttu-id="02a04-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="02a04-109">Attribute</span></span>|<span data-ttu-id="02a04-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="02a04-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02a04-111">name</span><span class="sxs-lookup"><span data-stu-id="02a04-111">name</span></span>|<span data-ttu-id="02a04-112">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="02a04-112">Required String attribute.</span></span><br /><br /> <span data-ttu-id="02a04-113">Contiene una clave definida por el usuario que identifica de forma única el tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="02a04-113">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="02a04-114">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="02a04-114">transportConfigurationType</span></span>|<span data-ttu-id="02a04-115">Una cadena que contiene el tipo que implementa el transporte concreto.</span><span class="sxs-lookup"><span data-stu-id="02a04-115">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02a04-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02a04-116">Child Elements</span></span>  

 <span data-ttu-id="02a04-117">None</span><span class="sxs-lookup"><span data-stu-id="02a04-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02a04-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02a04-118">Parent Elements</span></span>  
  
|<span data-ttu-id="02a04-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="02a04-119">Element</span></span>|<span data-ttu-id="02a04-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="02a04-120">Description</span></span>|  
|-------------|-----------------|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|<span data-ttu-id="02a04-121">Una colección de tipos que implementan el transporte concreto.</span><span class="sxs-lookup"><span data-stu-id="02a04-121">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02a04-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02a04-122">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="02a04-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="02a04-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="02a04-124">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="02a04-124">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
