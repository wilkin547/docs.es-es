---
title: '&lt;add&gt; de &lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: e21c3ca665d6a75394d70da43ec2044e00f16429
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145489"
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a><span data-ttu-id="9b735-102">&lt;add&gt; de &lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="9b735-102">&lt;add&gt; of &lt;protocolMapping&gt;</span></span>
<span data-ttu-id="9b735-103">Representa una asignación de protocolo predeterminado entre un esquema de protocolo de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y un enlace de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9b735-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="9b735-104">Al crear puntos de conexión predeterminados en tiempo de ejecución, WCF examina las asignaciones configuradas y decide qué enlace usar para una determinada dirección base.</span><span class="sxs-lookup"><span data-stu-id="9b735-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="9b735-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9b735-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9b735-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="9b735-106">\<protocolMapping></span></span>  
<span data-ttu-id="9b735-107">\<add></span><span class="sxs-lookup"><span data-stu-id="9b735-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b735-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b735-108">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b735-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9b735-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b735-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9b735-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b735-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b735-111">Attributes</span></span>  
  
|<span data-ttu-id="9b735-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b735-112">Element</span></span>|<span data-ttu-id="9b735-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b735-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b735-114">enlace</span><span class="sxs-lookup"><span data-stu-id="9b735-114">binding</span></span>|<span data-ttu-id="9b735-115">Cadena que especifica el tipo de enlace que se va a usar para un extremo durante la creación del extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9b735-115">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="9b735-116">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9b735-116">bindingConfiguration</span></span>|<span data-ttu-id="9b735-117">Cadena que especifica el nombre de la sección de configuración de enlace a la que se va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="9b735-117">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="9b735-118">scheme</span><span class="sxs-lookup"><span data-stu-id="9b735-118">scheme</span></span>|<span data-ttu-id="9b735-119">Esquema de protocolos de transporte que se va a utilizar para el punto de conexión predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9b735-119">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b735-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9b735-120">Child Elements</span></span>  
 <span data-ttu-id="9b735-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9b735-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b735-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9b735-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9b735-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b735-123">Element</span></span>|<span data-ttu-id="9b735-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b735-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b735-125">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="9b735-125">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="9b735-126">Representa una sección de configuración para definir las asignaciones de protocolos predeterminados entre esquemas de protocolos de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y enlaces de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9b735-126">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b735-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b735-127">Example</span></span>  
 <span data-ttu-id="9b735-128">En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="9b735-128">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="9b735-129">Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="9b735-129">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="9b735-130">O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="9b735-130">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="9b735-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b735-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
