---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: d6f0e4741aa10bff450a29cfd7a9e63e226c6495
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498887"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="040ae-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="040ae-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="040ae-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="040ae-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="040ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="040ae-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="040ae-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="040ae-105">Methods</span></span>  
 <span data-ttu-id="040ae-106">La clase ServiceDebugBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="040ae-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="040ae-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="040ae-107">Properties</span></span>  
 <span data-ttu-id="040ae-108">La clase ServiceDebugBehavior posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="040ae-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="040ae-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="040ae-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="040ae-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="040ae-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="040ae-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="040ae-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="040ae-112">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="040ae-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="040ae-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="040ae-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="040ae-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="040ae-114">Data type: string</span></span>  
  
 <span data-ttu-id="040ae-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="040ae-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="040ae-116">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="040ae-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="040ae-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="040ae-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="040ae-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="040ae-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="040ae-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="040ae-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="040ae-120">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="040ae-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="040ae-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="040ae-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="040ae-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="040ae-122">Data type: string</span></span>  
  
 <span data-ttu-id="040ae-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="040ae-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="040ae-124">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="040ae-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="040ae-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="040ae-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="040ae-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="040ae-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="040ae-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="040ae-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="040ae-128">Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.</span><span class="sxs-lookup"><span data-stu-id="040ae-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="040ae-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="040ae-129">Requirements</span></span>  
  
|<span data-ttu-id="040ae-130">MOF</span><span class="sxs-lookup"><span data-stu-id="040ae-130">MOF</span></span>|<span data-ttu-id="040ae-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="040ae-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="040ae-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="040ae-132">Namespace</span></span>|<span data-ttu-id="040ae-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="040ae-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="040ae-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="040ae-134">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
