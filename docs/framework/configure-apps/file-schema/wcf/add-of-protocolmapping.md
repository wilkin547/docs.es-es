---
title: <add> de <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850377"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="eee73-102">\<Agregar > de \<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="eee73-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="eee73-103">Representa una asignación de protocolo predeterminada entre un esquema de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y un enlace Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eee73-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="eee73-104">Al crear puntos de conexión predeterminados en tiempo de ejecución, WCF examina las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.</span><span class="sxs-lookup"><span data-stu-id="eee73-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="eee73-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eee73-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eee73-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="eee73-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="eee73-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> protocolMapping**](protocolmapping.md)</span><span class="sxs-lookup"><span data-stu-id="eee73-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)</span></span>\
<span data-ttu-id="eee73-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="eee73-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee73-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eee73-109">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eee73-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eee73-110">Attributes and Elements</span></span>  
 <span data-ttu-id="eee73-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eee73-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eee73-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="eee73-112">Attributes</span></span>  
  
|<span data-ttu-id="eee73-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="eee73-113">Element</span></span>|<span data-ttu-id="eee73-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eee73-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eee73-115">enlace</span><span class="sxs-lookup"><span data-stu-id="eee73-115">binding</span></span>|<span data-ttu-id="eee73-116">Cadena que especifica el tipo de enlace que se va a usar para un extremo durante la creación del extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="eee73-116">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="eee73-117">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eee73-117">bindingConfiguration</span></span>|<span data-ttu-id="eee73-118">Cadena que especifica el nombre de la sección de configuración de enlace a la que se va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="eee73-118">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="eee73-119">scheme</span><span class="sxs-lookup"><span data-stu-id="eee73-119">scheme</span></span>|<span data-ttu-id="eee73-120">Esquema de protocolos de transporte que se va a utilizar para el extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="eee73-120">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eee73-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eee73-121">Child Elements</span></span>  
 <span data-ttu-id="eee73-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eee73-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eee73-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eee73-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eee73-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="eee73-124">Element</span></span>|<span data-ttu-id="eee73-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eee73-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eee73-126">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="eee73-126">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="eee73-127">Representa una sección de configuración para definir las asignaciones de protocolo predeterminadas entre los esquemas de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y los enlaces de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eee73-127">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eee73-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eee73-128">Example</span></span>  
 <span data-ttu-id="eee73-129">En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="eee73-129">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="eee73-130">Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="eee73-130">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="eee73-131">O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="eee73-131">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eee73-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="eee73-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
