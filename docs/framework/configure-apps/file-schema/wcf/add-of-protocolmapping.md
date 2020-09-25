---
title: <add> de <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 46ba21b65f524f88bfce81739f0cd73040a2ad45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205014"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="917eb-102">\<add> de \<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="917eb-102">\<add> of \<protocolMapping></span></span>

<span data-ttu-id="917eb-103">Representa una asignación de protocolo predeterminada entre un esquema de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y un enlace Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="917eb-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="917eb-104">Al crear puntos de conexión predeterminados en tiempo de ejecución, WCF examina las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.</span><span class="sxs-lookup"><span data-stu-id="917eb-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="917eb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="917eb-105">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="917eb-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="917eb-106">Attributes and Elements</span></span>  

 <span data-ttu-id="917eb-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="917eb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="917eb-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="917eb-108">Attributes</span></span>  
  
|<span data-ttu-id="917eb-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="917eb-109">Element</span></span>|<span data-ttu-id="917eb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="917eb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="917eb-111">binding</span><span class="sxs-lookup"><span data-stu-id="917eb-111">binding</span></span>|<span data-ttu-id="917eb-112">Cadena que especifica el tipo de enlace que se va a usar para un extremo durante la creación del extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="917eb-112">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="917eb-113">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="917eb-113">bindingConfiguration</span></span>|<span data-ttu-id="917eb-114">Cadena que especifica el nombre de la sección de configuración de enlace a la que se va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="917eb-114">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="917eb-115">scheme</span><span class="sxs-lookup"><span data-stu-id="917eb-115">scheme</span></span>|<span data-ttu-id="917eb-116">Esquema de protocolos de transporte que se va a utilizar para el extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="917eb-116">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="917eb-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="917eb-117">Child Elements</span></span>  

 <span data-ttu-id="917eb-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="917eb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="917eb-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="917eb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="917eb-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="917eb-120">Element</span></span>|<span data-ttu-id="917eb-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="917eb-121">Description</span></span>|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="917eb-122">Representa una sección de configuración para definir las asignaciones de protocolo predeterminadas entre los esquemas de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y los enlaces de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="917eb-122">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="917eb-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="917eb-123">Example</span></span>  

 <span data-ttu-id="917eb-124">En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="917eb-124">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="917eb-125">Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="917eb-125">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="917eb-126">O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="917eb-126">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="917eb-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="917eb-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
