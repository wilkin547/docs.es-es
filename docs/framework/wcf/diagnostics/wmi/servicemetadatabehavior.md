---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976143"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="ecc24-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="ecc24-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="ecc24-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="ecc24-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecc24-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="ecc24-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ecc24-105">Methods</span></span>  
 <span data-ttu-id="ecc24-106">La clase ServiceMetadataBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ecc24-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ecc24-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ecc24-107">Properties</span></span>  
 <span data-ttu-id="ecc24-108">La clase ServiceMetadataBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="ecc24-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="ecc24-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="ecc24-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="ecc24-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ecc24-110">Data type: string</span></span>  
  
 <span data-ttu-id="ecc24-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ecc24-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ecc24-112">Establece la ubicación a la que el servicio redirige las solicitudes de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ecc24-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="ecc24-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="ecc24-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="ecc24-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="ecc24-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ecc24-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ecc24-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ecc24-116">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="ecc24-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="ecc24-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="ecc24-117">HttpGetUrl</span></span>  
 <span data-ttu-id="ecc24-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ecc24-118">Data type: string</span></span>  
  
 <span data-ttu-id="ecc24-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ecc24-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ecc24-120">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="ecc24-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="ecc24-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="ecc24-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="ecc24-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="ecc24-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="ecc24-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ecc24-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ecc24-124">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="ecc24-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="ecc24-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="ecc24-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="ecc24-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ecc24-126">Data type: string</span></span>  
  
 <span data-ttu-id="ecc24-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ecc24-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ecc24-128">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ecc24-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc24-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecc24-129">Requirements</span></span>  
  
|<span data-ttu-id="ecc24-130">MOF</span><span class="sxs-lookup"><span data-stu-id="ecc24-130">MOF</span></span>|<span data-ttu-id="ecc24-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ecc24-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ecc24-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ecc24-132">Namespace</span></span>|<span data-ttu-id="ecc24-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ecc24-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ecc24-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecc24-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
