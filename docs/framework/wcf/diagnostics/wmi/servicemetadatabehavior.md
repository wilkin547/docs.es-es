---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160334"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="cf7b9-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="cf7b9-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="cf7b9-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="cf7b9-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf7b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf7b9-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cf7b9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cf7b9-105">Methods</span></span>  
 <span data-ttu-id="cf7b9-106">La clase ServiceMetadataBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="cf7b9-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cf7b9-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cf7b9-107">Properties</span></span>  
 <span data-ttu-id="cf7b9-108">La clase ServiceMetadataBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf7b9-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="cf7b9-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="cf7b9-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="cf7b9-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="cf7b9-110">Data type: string</span></span>  
  
 <span data-ttu-id="cf7b9-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cf7b9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf7b9-112">Establece la ubicación a la que el servicio redirige las solicitudes de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="cf7b9-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="cf7b9-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="cf7b9-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="cf7b9-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="cf7b9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf7b9-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cf7b9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf7b9-116">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="cf7b9-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="cf7b9-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="cf7b9-117">HttpGetUrl</span></span>  
 <span data-ttu-id="cf7b9-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="cf7b9-118">Data type: string</span></span>  
  
 <span data-ttu-id="cf7b9-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cf7b9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf7b9-120">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="cf7b9-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="cf7b9-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="cf7b9-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="cf7b9-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="cf7b9-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="cf7b9-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cf7b9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf7b9-124">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="cf7b9-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="cf7b9-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="cf7b9-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="cf7b9-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="cf7b9-126">Data type: string</span></span>  
  
 <span data-ttu-id="cf7b9-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cf7b9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cf7b9-128">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cf7b9-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf7b9-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf7b9-129">Requirements</span></span>  
  
|<span data-ttu-id="cf7b9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="cf7b9-130">MOF</span></span>|<span data-ttu-id="cf7b9-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cf7b9-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cf7b9-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="cf7b9-132">Namespace</span></span>|<span data-ttu-id="cf7b9-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cf7b9-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf7b9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf7b9-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
