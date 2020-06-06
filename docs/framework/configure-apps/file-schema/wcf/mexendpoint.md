---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855114"
---
# \<mexEndpoint>
<span data-ttu-id="10747-101">Este elemento de configuración define un punto de conexión estándar con un contrato IMetadataExchange fijo.</span><span class="sxs-lookup"><span data-stu-id="10747-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="10747-102">Puesto que todos los puntos de conexión del intercambio de metadatos especifican IMetadataExchange como su contrato, puede usar este punto estándar en lugar de definir uno para sí mismo.</span><span class="sxs-lookup"><span data-stu-id="10747-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="10747-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10747-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10747-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="10747-104">Attributes and Elements</span></span>  
 <span data-ttu-id="10747-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="10747-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10747-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="10747-106">Attributes</span></span>  
  
|<span data-ttu-id="10747-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="10747-107">Attribute</span></span>|<span data-ttu-id="10747-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="10747-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10747-109">name</span><span class="sxs-lookup"><span data-stu-id="10747-109">name</span></span>|<span data-ttu-id="10747-110">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="10747-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="10747-111">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="10747-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10747-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="10747-112">Child Elements</span></span>  
 <span data-ttu-id="10747-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="10747-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10747-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="10747-114">Parent Elements</span></span>  
  
|<span data-ttu-id="10747-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="10747-115">Element</span></span>|<span data-ttu-id="10747-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="10747-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="10747-117">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="10747-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
