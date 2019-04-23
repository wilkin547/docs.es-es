---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: e26044340bda84fe38b7e286edf833affa94b86c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118221"
---
# <a name="protocolmapping"></a><span data-ttu-id="9baa3-101">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="9baa3-101">\<protocolMapping></span></span>
<span data-ttu-id="9baa3-102">Representa una sección de configuración para definir un conjunto de asignación de protocolo predeterminado entre los esquemas de protocolos de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y enlaces WCF.</span><span class="sxs-lookup"><span data-stu-id="9baa3-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="9baa3-103">Al crear puntos de conexión predeterminados en tiempo de ejecución, Windows Communication Foundation (WCF) examina las asignaciones configuradas y decide qué enlace usar para una determinada dirección base.</span><span class="sxs-lookup"><span data-stu-id="9baa3-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[<span data-ttu-id="9baa3-104">**\<system.serviceModel>**</span><span class="sxs-lookup"><span data-stu-id="9baa3-104">**\<system.serviceModel>**</span></span>](system-servicemodel.md)  
<span data-ttu-id="9baa3-105">&nbsp;&nbsp;**\<protocolMapping>**</span><span class="sxs-lookup"><span data-stu-id="9baa3-105">&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9baa3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9baa3-106">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9baa3-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9baa3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9baa3-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9baa3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9baa3-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9baa3-109">Attributes</span></span>  
 <span data-ttu-id="9baa3-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9baa3-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9baa3-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9baa3-111">Child Elements</span></span>  
  
|<span data-ttu-id="9baa3-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9baa3-112">Element</span></span>|<span data-ttu-id="9baa3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9baa3-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9baa3-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="9baa3-114">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="9baa3-115">Contiene una asignación de protocolo predeterminado entre un esquema de protocolo de transporte (por ejemplo, http, net.tcp, net.pipe, etc.) y un enlace WCF.</span><span class="sxs-lookup"><span data-stu-id="9baa3-115">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9baa3-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9baa3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9baa3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9baa3-117">Element</span></span>|<span data-ttu-id="9baa3-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9baa3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9baa3-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9baa3-119">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="9baa3-120">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="9baa3-120">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9baa3-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9baa3-121">Example</span></span>  
 <span data-ttu-id="9baa3-122">En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="9baa3-122">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="9baa3-123">Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="9baa3-123">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="9baa3-124">O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="9baa3-124">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9baa3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9baa3-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
