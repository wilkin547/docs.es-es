---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855114"
---
# <a name="mexendpoint"></a><span data-ttu-id="ce243-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="ce243-101">\<mexEndpoint></span></span>
<span data-ttu-id="ce243-102">Este elemento de configuración define un punto de conexión estándar con un contrato IMetadataExchange fijo.</span><span class="sxs-lookup"><span data-stu-id="ce243-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="ce243-103">Puesto que todos los puntos de conexión del intercambio de metadatos especifican IMetadataExchange como su contrato, puede usar este punto estándar en lugar de definir uno para sí mismo.</span><span class="sxs-lookup"><span data-stu-id="ce243-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
<span data-ttu-id="ce243-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce243-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ce243-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ce243-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ce243-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="ce243-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="ce243-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> mexEndpoint**</span><span class="sxs-lookup"><span data-stu-id="ce243-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce243-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce243-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce243-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ce243-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ce243-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ce243-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce243-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ce243-111">Attributes</span></span>  
  
|<span data-ttu-id="ce243-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="ce243-112">Attribute</span></span>|<span data-ttu-id="ce243-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ce243-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce243-114">name</span><span class="sxs-lookup"><span data-stu-id="ce243-114">name</span></span>|<span data-ttu-id="ce243-115">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="ce243-115">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="ce243-116">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="ce243-116">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce243-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ce243-117">Child Elements</span></span>  
 <span data-ttu-id="ce243-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ce243-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce243-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ce243-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ce243-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce243-120">Element</span></span>|<span data-ttu-id="ce243-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ce243-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce243-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ce243-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="ce243-123">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="ce243-123">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
