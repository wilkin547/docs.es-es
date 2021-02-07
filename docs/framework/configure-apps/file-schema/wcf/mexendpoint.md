---
description: 'Más información acerca de: <mexEndpoint>'
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 1872b6104aaaaa2787ca3f359026552499bade9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684417"
---
# \<mexEndpoint>

<span data-ttu-id="ce2d5-102">Este elemento de configuración define un punto de conexión estándar con un contrato IMetadataExchange fijo.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="ce2d5-103">Puesto que todos los puntos de conexión del intercambio de metadatos especifican IMetadataExchange como su contrato, puede usar este punto estándar en lugar de definir uno para sí mismo.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="ce2d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce2d5-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce2d5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ce2d5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ce2d5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce2d5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ce2d5-107">Attributes</span></span>  
  
|<span data-ttu-id="ce2d5-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ce2d5-108">Attribute</span></span>|<span data-ttu-id="ce2d5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce2d5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce2d5-110">name</span><span class="sxs-lookup"><span data-stu-id="ce2d5-110">name</span></span>|<span data-ttu-id="ce2d5-111">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-111">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="ce2d5-112">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-112">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce2d5-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ce2d5-113">Child Elements</span></span>  

 <span data-ttu-id="ce2d5-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce2d5-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ce2d5-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ce2d5-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce2d5-116">Element</span></span>|<span data-ttu-id="ce2d5-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce2d5-117">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="ce2d5-118">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-118">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
