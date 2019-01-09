---
title: '&lt;add&gt; de &lt;transportConfigurationType&gt;'
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: 1079b25ce137dc89fc31f46a11f3720486462021
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149142"
---
# <a name="ltaddgt-of-lttransportconfigurationtypegt"></a><span data-ttu-id="e684b-102">&lt;add&gt; de &lt;transportConfigurationType&gt;</span><span class="sxs-lookup"><span data-stu-id="e684b-102">&lt;add&gt; of &lt;transportConfigurationType&gt;</span></span>
<span data-ttu-id="e684b-103">Este elemento es una par clave-valor, que identifica el tipo de un transporte determinado.</span><span class="sxs-lookup"><span data-stu-id="e684b-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="e684b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e684b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e684b-105">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="e684b-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="e684b-106">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="e684b-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="e684b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e684b-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e684b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e684b-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e684b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e684b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e684b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e684b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e684b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e684b-111">Attributes</span></span>  
  
|<span data-ttu-id="e684b-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="e684b-112">Attribute</span></span>|<span data-ttu-id="e684b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e684b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e684b-114">name</span><span class="sxs-lookup"><span data-stu-id="e684b-114">name</span></span>|<span data-ttu-id="e684b-115">Atributo de cadena necesario.</span><span class="sxs-lookup"><span data-stu-id="e684b-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="e684b-116">Contiene una clave definida por el usuario que identifica de forma única el tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="e684b-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="e684b-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="e684b-117">transportConfigurationType</span></span>|<span data-ttu-id="e684b-118">Una cadena que contiene el tipo que implementa el transporte concreto.</span><span class="sxs-lookup"><span data-stu-id="e684b-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e684b-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e684b-119">Child Elements</span></span>  
 <span data-ttu-id="e684b-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e684b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e684b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e684b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e684b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="e684b-122">Element</span></span>|<span data-ttu-id="e684b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="e684b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e684b-124">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="e684b-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="e684b-125">Una colección de tipos que implementan el transporte concreto.</span><span class="sxs-lookup"><span data-stu-id="e684b-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e684b-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e684b-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="e684b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e684b-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="e684b-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e684b-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
