---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090919"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="cfc91-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="cfc91-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="cfc91-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="cfc91-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfc91-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfc91-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="cfc91-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cfc91-105">Methods</span></span>  
 <span data-ttu-id="cfc91-106">La clase ServiceDebugBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="cfc91-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cfc91-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cfc91-107">Properties</span></span>  
 <span data-ttu-id="cfc91-108">La clase ServiceDebugBehavior posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="cfc91-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="cfc91-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="cfc91-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="cfc91-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="cfc91-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="cfc91-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cfc91-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cfc91-112">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="cfc91-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="cfc91-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="cfc91-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="cfc91-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="cfc91-114">Data type: string</span></span>  
  
 <span data-ttu-id="cfc91-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cfc91-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cfc91-116">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="cfc91-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="cfc91-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="cfc91-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="cfc91-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="cfc91-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="cfc91-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cfc91-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cfc91-120">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="cfc91-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="cfc91-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="cfc91-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="cfc91-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="cfc91-122">Data type: string</span></span>  
  
 <span data-ttu-id="cfc91-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cfc91-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cfc91-124">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cfc91-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="cfc91-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="cfc91-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="cfc91-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="cfc91-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="cfc91-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="cfc91-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cfc91-128">Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.</span><span class="sxs-lookup"><span data-stu-id="cfc91-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfc91-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfc91-129">Requirements</span></span>  
  
|<span data-ttu-id="cfc91-130">MOF</span><span class="sxs-lookup"><span data-stu-id="cfc91-130">MOF</span></span>|<span data-ttu-id="cfc91-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cfc91-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cfc91-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="cfc91-132">Namespace</span></span>|<span data-ttu-id="cfc91-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cfc91-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfc91-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfc91-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
