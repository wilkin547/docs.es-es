---
title: '&lt;protocolMapping&gt;'
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: 4afdaaa62c1ac3241eb7382d0995bed51bde73e2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748911"
---
# <a name="ltprotocolmappinggt"></a><span data-ttu-id="11212-102">&lt;protocolMapping&gt;</span><span class="sxs-lookup"><span data-stu-id="11212-102">&lt;protocolMapping&gt;</span></span>
<span data-ttu-id="11212-103">Representa una sección de configuración para definir un conjunto de asignación de protocolo predeterminado entre los esquemas de protocolos de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y enlaces de WCF.</span><span class="sxs-lookup"><span data-stu-id="11212-103">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="11212-104">Al crear extremos predeterminados en tiempo de ejecución, Windows Communication Foundation (WCF) examina las asignaciones configuradas y decide qué enlace usar para una determinada dirección base.</span><span class="sxs-lookup"><span data-stu-id="11212-104">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
 <span data-ttu-id="11212-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="11212-105">\<system.serviceModel></span></span>  
<span data-ttu-id="11212-106">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="11212-106">\<protocolMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11212-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11212-107">Syntax</span></span>  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="11212-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="11212-108">Attributes and Elements</span></span>  
 <span data-ttu-id="11212-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="11212-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11212-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="11212-110">Attributes</span></span>  
 <span data-ttu-id="11212-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="11212-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="11212-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="11212-112">Child Elements</span></span>  
  
|<span data-ttu-id="11212-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="11212-113">Element</span></span>|<span data-ttu-id="11212-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="11212-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11212-115">\<filtros ></span><span class="sxs-lookup"><span data-stu-id="11212-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="11212-116">Contiene una asignación de protocolo predeterminado entre un esquema de protocolo de transporte (p. ej., http, net.tcp, net.pipe, etc.) y un enlace WCF.</span><span class="sxs-lookup"><span data-stu-id="11212-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11212-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="11212-117">Parent Elements</span></span>  
  
|<span data-ttu-id="11212-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="11212-118">Element</span></span>|<span data-ttu-id="11212-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="11212-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11212-120">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="11212-120">system.ServiceModel</span></span>|<span data-ttu-id="11212-121">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="11212-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="11212-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11212-122">Example</span></span>  
 <span data-ttu-id="11212-123">En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="11212-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="11212-124">Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="11212-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="11212-125">O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="11212-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a><span data-ttu-id="11212-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="11212-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
