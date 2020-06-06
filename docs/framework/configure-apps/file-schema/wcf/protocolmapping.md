---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400018"
---
# \<protocolMapping>
<span data-ttu-id="965f4-101">Representa una sección de configuración para definir un conjunto de asignaciones de protocolos predeterminados entre esquemas de protocolos de transporte (ej., http, net.tcp, net.pipe, etc.) y enlaces WCF.</span><span class="sxs-lookup"><span data-stu-id="965f4-101">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="965f4-102">Al crear puntos de conexión predeterminados en tiempo de ejecución, Windows Communication Foundation (WCF) examina las asignaciones configuradas y decide qué enlace usar para una dirección base determinada.</span><span class="sxs-lookup"><span data-stu-id="965f4-102">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a><span data-ttu-id="965f4-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="965f4-103">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="965f4-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="965f4-104">Attributes and Elements</span></span>  
 <span data-ttu-id="965f4-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="965f4-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="965f4-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="965f4-106">Attributes</span></span>  
 <span data-ttu-id="965f4-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="965f4-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="965f4-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="965f4-108">Child Elements</span></span>  
  
|<span data-ttu-id="965f4-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="965f4-109">Element</span></span>|<span data-ttu-id="965f4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="965f4-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="965f4-111">Contiene una asignación de protocolo predeterminado entre un esquema de protocolos de transporte (ej., http, net.tcp, net.pipe, etc.) y un enlace WCF.</span><span class="sxs-lookup"><span data-stu-id="965f4-111">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="965f4-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="965f4-112">Parent Elements</span></span>  
  
|<span data-ttu-id="965f4-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="965f4-113">Element</span></span>|<span data-ttu-id="965f4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="965f4-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="965f4-115">Elemento raíz de todos los elementos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="965f4-115">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="965f4-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="965f4-116">Example</span></span>  
 <span data-ttu-id="965f4-117">En el siguiente ejemplo de configuración se muestra la asignación de protocolo predeterminado en el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="965f4-117">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="965f4-118">Puede invalidar esta asignación predeterminada en el nivel del equipo modificando el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="965f4-118">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="965f4-119">O bien, si solo deseara invalidarlo dentro del ámbito de una aplicación, puede invalidar esta sección dentro del archivo de configuración de la aplicación y cambiar la asignación para los esquemas de protocolos individuales.</span><span class="sxs-lookup"><span data-stu-id="965f4-119">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="965f4-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="965f4-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
