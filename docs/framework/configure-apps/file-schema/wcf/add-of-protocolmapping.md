---
description: 'Más información sobre: <add> de <protocolMapping>'
title: <add> de <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 530ef6b2893eb55a979aba2ef7ec21efffc3070a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750252"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="f15e5-103">\<add> de \<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="f15e5-103">\<add> of \<protocolMapping></span></span>

<span data-ttu-id="f15e5-104">Representa una asignación de protocolo predeterminada entre un esquema de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y un enlace Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f15e5-104">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="f15e5-105">Al crear puntos de conexión predeterminados en tiempo de ejecución, WCF examina las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.</span><span class="sxs-lookup"><span data-stu-id="f15e5-105">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="f15e5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f15e5-106">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f15e5-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f15e5-107">Attributes and Elements</span></span>  

 <span data-ttu-id="f15e5-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f15e5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f15e5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f15e5-109">Attributes</span></span>  
  
|<span data-ttu-id="f15e5-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f15e5-110">Element</span></span>|<span data-ttu-id="f15e5-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f15e5-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f15e5-112">binding</span><span class="sxs-lookup"><span data-stu-id="f15e5-112">binding</span></span>|<span data-ttu-id="f15e5-113">Cadena que especifica el tipo de enlace que se va a usar para un extremo durante la creación del extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f15e5-113">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="f15e5-114">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="f15e5-114">bindingConfiguration</span></span>|<span data-ttu-id="f15e5-115">Cadena que especifica el nombre de la sección de configuración de enlace a la que se va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="f15e5-115">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="f15e5-116">scheme</span><span class="sxs-lookup"><span data-stu-id="f15e5-116">scheme</span></span>|<span data-ttu-id="f15e5-117">Esquema de protocolos de transporte que se va a utilizar para el extremo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f15e5-117">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f15e5-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f15e5-118">Child Elements</span></span>  

 <span data-ttu-id="f15e5-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f15e5-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f15e5-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f15e5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f15e5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f15e5-121">Element</span></span>|<span data-ttu-id="f15e5-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f15e5-122">Description</span></span>|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="f15e5-123">Representa una sección de configuración para definir las asignaciones de protocolo predeterminadas entre los esquemas de protocolo de transporte (por ejemplo, http, net. TCP, net. Pipe, etc.) y los enlaces de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f15e5-123">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f15e5-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f15e5-124">Example</span></span>  

 <span data-ttu-id="f15e5-125">En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="f15e5-125">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="f15e5-126">Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="f15e5-126">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="f15e5-127">O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="f15e5-127">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f15e5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f15e5-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
