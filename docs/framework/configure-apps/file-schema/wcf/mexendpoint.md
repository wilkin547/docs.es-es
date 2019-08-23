---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 78788f9dfbf6cdf3439fd6e33eddfe721e49840d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931255"
---
# <a name="mexendpoint"></a><span data-ttu-id="2c834-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="2c834-101">\<mexEndpoint></span></span>
<span data-ttu-id="2c834-102">Este elemento de configuración define un punto de conexión estándar con un contrato IMetadataExchange fijo.</span><span class="sxs-lookup"><span data-stu-id="2c834-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="2c834-103">Puesto que todos los puntos de conexión del intercambio de metadatos especifican IMetadataExchange como su contrato, puede usar este punto estándar en lugar de definir uno para sí mismo.</span><span class="sxs-lookup"><span data-stu-id="2c834-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="2c834-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2c834-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2c834-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="2c834-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c834-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c834-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c834-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2c834-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2c834-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2c834-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c834-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="2c834-109">Attributes</span></span>  
  
|<span data-ttu-id="2c834-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="2c834-110">Attribute</span></span>|<span data-ttu-id="2c834-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2c834-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c834-112">name</span><span class="sxs-lookup"><span data-stu-id="2c834-112">name</span></span>|<span data-ttu-id="2c834-113">Cadena que especifica el nombre de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="2c834-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="2c834-114">El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.</span><span class="sxs-lookup"><span data-stu-id="2c834-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c834-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2c834-115">Child Elements</span></span>  
 <span data-ttu-id="2c834-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2c834-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c834-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2c834-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2c834-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c834-118">Element</span></span>|<span data-ttu-id="2c834-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2c834-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c834-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="2c834-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="2c834-121">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="2c834-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
