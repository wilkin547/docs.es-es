---
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964092"
---
# <a name="channel-class"></a><span data-ttu-id="1028b-102">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="1028b-102">Channel class</span></span>
<span data-ttu-id="1028b-103">Canal</span><span class="sxs-lookup"><span data-stu-id="1028b-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1028b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1028b-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1028b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1028b-105">Methods</span></span>  
 <span data-ttu-id="1028b-106">La clase Canal no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1028b-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1028b-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1028b-107">Properties</span></span>  
 <span data-ttu-id="1028b-108">La clase Canal tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="1028b-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="1028b-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="1028b-109">LocalAddress</span></span>  
 <span data-ttu-id="1028b-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1028b-110">Data type: string</span></span>  
  
 <span data-ttu-id="1028b-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1028b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1028b-112">punto de conexión local para el canal.</span><span class="sxs-lookup"><span data-stu-id="1028b-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="1028b-113">ref</span><span class="sxs-lookup"><span data-stu-id="1028b-113">ref</span></span>  
 <span data-ttu-id="1028b-114">Tipo de datos: punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1028b-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="1028b-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1028b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1028b-116">Una referencia al extremo al que se conecta el canal.</span><span class="sxs-lookup"><span data-stu-id="1028b-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="1028b-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="1028b-117">RemoteAddress</span></span>  
 <span data-ttu-id="1028b-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1028b-118">Data type: string</span></span>  
  
 <span data-ttu-id="1028b-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1028b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1028b-120">Dirección remota asociada al canal.</span><span class="sxs-lookup"><span data-stu-id="1028b-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="1028b-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="1028b-121">SessionId</span></span>  
 <span data-ttu-id="1028b-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1028b-122">Data type: string</span></span>  
  
 <span data-ttu-id="1028b-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1028b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1028b-124">Identificador de la sesión actual, si lo hubiera.</span><span class="sxs-lookup"><span data-stu-id="1028b-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="1028b-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="1028b-125">Type</span></span>  
 <span data-ttu-id="1028b-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1028b-126">Data type: string</span></span>  
  
 <span data-ttu-id="1028b-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1028b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1028b-128">El tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="1028b-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1028b-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1028b-129">Requirements</span></span>  
  
|<span data-ttu-id="1028b-130">MOF</span><span class="sxs-lookup"><span data-stu-id="1028b-130">MOF</span></span>|<span data-ttu-id="1028b-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1028b-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1028b-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1028b-132">Namespace</span></span>|<span data-ttu-id="1028b-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1028b-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1028b-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1028b-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
