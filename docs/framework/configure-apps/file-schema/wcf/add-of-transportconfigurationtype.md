---
title: <add> de <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: c71a58b13e89bedb5eed24d784c82fb1525f7625
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126729"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="9a2fd-102">\<Agregar > de \<transportConfigurationType ></span><span class="sxs-lookup"><span data-stu-id="9a2fd-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="9a2fd-103">Este elemento es una par clave-valor, que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="9a2fd-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="9a2fd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9a2fd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9a2fd-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="9a2fd-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="9a2fd-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="9a2fd-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="9a2fd-107">\<add></span><span class="sxs-lookup"><span data-stu-id="9a2fd-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a2fd-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a2fd-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a2fd-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9a2fd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9a2fd-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9a2fd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a2fd-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9a2fd-111">Attributes</span></span>  
  
|<span data-ttu-id="9a2fd-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9a2fd-112">Attribute</span></span>|<span data-ttu-id="9a2fd-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a2fd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a2fd-114">name</span><span class="sxs-lookup"><span data-stu-id="9a2fd-114">name</span></span>|<span data-ttu-id="9a2fd-115">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="9a2fd-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="9a2fd-116">Contiene una clave definida por el usuario que identifica de forma única el tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="9a2fd-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="9a2fd-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="9a2fd-117">transportConfigurationType</span></span>|<span data-ttu-id="9a2fd-118">Una cadena que contiene el tipo que implementa el transporte concreto.</span><span class="sxs-lookup"><span data-stu-id="9a2fd-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a2fd-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9a2fd-119">Child Elements</span></span>  
 <span data-ttu-id="9a2fd-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9a2fd-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a2fd-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a2fd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9a2fd-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a2fd-122">Element</span></span>|<span data-ttu-id="9a2fd-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a2fd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a2fd-124">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="9a2fd-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="9a2fd-125">Una colección de tipos que implementan el transporte concreto.</span><span class="sxs-lookup"><span data-stu-id="9a2fd-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9a2fd-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a2fd-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="9a2fd-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a2fd-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="9a2fd-128">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="9a2fd-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
