---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 19a04b6432f1ecc38a3b906b7e677175863134db
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188838"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="3f2f4-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="3f2f4-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="3f2f4-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="3f2f4-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f2f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f2f4-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="3f2f4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3f2f4-105">Methods</span></span>  
 <span data-ttu-id="3f2f4-106">La clase ServiceMetadataBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="3f2f4-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3f2f4-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3f2f4-107">Properties</span></span>  
 <span data-ttu-id="3f2f4-108">La clase ServiceMetadataBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="3f2f4-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="3f2f4-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="3f2f4-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="3f2f4-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3f2f4-110">Data type: string</span></span>  
  
 <span data-ttu-id="3f2f4-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3f2f4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f2f4-112">Establece la ubicación a la que el servicio redirige las solicitudes de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="3f2f4-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="3f2f4-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="3f2f4-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="3f2f4-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="3f2f4-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="3f2f4-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3f2f4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f2f4-116">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="3f2f4-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="3f2f4-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="3f2f4-117">HttpGetUrl</span></span>  
 <span data-ttu-id="3f2f4-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3f2f4-118">Data type: string</span></span>  
  
 <span data-ttu-id="3f2f4-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3f2f4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f2f4-120">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="3f2f4-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="3f2f4-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="3f2f4-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="3f2f4-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="3f2f4-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="3f2f4-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3f2f4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f2f4-124">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="3f2f4-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="3f2f4-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="3f2f4-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="3f2f4-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3f2f4-126">Data type: string</span></span>  
  
 <span data-ttu-id="3f2f4-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3f2f4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3f2f4-128">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3f2f4-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f2f4-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f2f4-129">Requirements</span></span>  
  
|<span data-ttu-id="3f2f4-130">MOF</span><span class="sxs-lookup"><span data-stu-id="3f2f4-130">MOF</span></span>|<span data-ttu-id="3f2f4-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3f2f4-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3f2f4-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="3f2f4-132">Namespace</span></span>|<span data-ttu-id="3f2f4-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3f2f4-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f2f4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f2f4-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
