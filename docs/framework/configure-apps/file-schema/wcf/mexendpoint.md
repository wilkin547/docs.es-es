---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 8fffcc05d5f53f719efce182083fbf103b1230ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772481"
---
# <a name="mexendpoint"></a><span data-ttu-id="ff3bf-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="ff3bf-101">\<mexEndpoint></span></span>
<span data-ttu-id="ff3bf-102">Este elemento de configuración define un punto de conexión estándar con un contrato IMetadataExchange fijo.</span><span class="sxs-lookup"><span data-stu-id="ff3bf-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="ff3bf-103">Puesto que todos los puntos de conexión del intercambio de metadatos especifican IMetadataExchange como su contrato, puede usar este punto estándar en lugar de definir uno para sí mismo.</span><span class="sxs-lookup"><span data-stu-id="ff3bf-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="ff3bf-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ff3bf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ff3bf-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ff3bf-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff3bf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff3bf-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff3bf-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ff3bf-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ff3bf-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ff3bf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff3bf-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff3bf-109">Attributes</span></span>  
  
|<span data-ttu-id="ff3bf-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="ff3bf-110">Attribute</span></span>|<span data-ttu-id="ff3bf-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff3bf-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff3bf-112">name</span><span class="sxs-lookup"><span data-stu-id="ff3bf-112">name</span></span>|<span data-ttu-id="ff3bf-113">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="ff3bf-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="ff3bf-114">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="ff3bf-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff3bf-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ff3bf-115">Child Elements</span></span>  
 <span data-ttu-id="ff3bf-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ff3bf-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff3bf-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ff3bf-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ff3bf-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff3bf-118">Element</span></span>|<span data-ttu-id="ff3bf-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff3bf-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff3bf-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ff3bf-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="ff3bf-121">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="ff3bf-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
