---
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 3fbf398cca7ae9adbbecb9439bf3cbd32eb03969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668397"
---
# <a name="channel-class"></a><span data-ttu-id="e2ac8-102">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="e2ac8-102">Channel class</span></span>
<span data-ttu-id="e2ac8-103">Canal</span><span class="sxs-lookup"><span data-stu-id="e2ac8-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ac8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2ac8-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e2ac8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e2ac8-105">Methods</span></span>  
 <span data-ttu-id="e2ac8-106">La clase Canal no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e2ac8-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e2ac8-107">Properties</span></span>  
 <span data-ttu-id="e2ac8-108">La clase Canal tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="e2ac8-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="e2ac8-109">LocalAddress</span></span>  
 <span data-ttu-id="e2ac8-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e2ac8-110">Data type: string</span></span>  
  
 <span data-ttu-id="e2ac8-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e2ac8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2ac8-112">punto de conexión local para el canal.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="e2ac8-113">ref</span><span class="sxs-lookup"><span data-stu-id="e2ac8-113">ref</span></span>  
 <span data-ttu-id="e2ac8-114">Tipo de datos: punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e2ac8-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="e2ac8-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e2ac8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2ac8-116">Una referencia al punto de conexión al que se conecta el canal.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="e2ac8-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="e2ac8-117">RemoteAddress</span></span>  
 <span data-ttu-id="e2ac8-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e2ac8-118">Data type: string</span></span>  
  
 <span data-ttu-id="e2ac8-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e2ac8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2ac8-120">Dirección remota asociada al canal.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="e2ac8-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="e2ac8-121">SessionId</span></span>  
 <span data-ttu-id="e2ac8-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e2ac8-122">Data type: string</span></span>  
  
 <span data-ttu-id="e2ac8-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e2ac8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2ac8-124">Identificador de la sesión actual, si lo hubiera.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="e2ac8-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="e2ac8-125">Type</span></span>  
 <span data-ttu-id="e2ac8-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e2ac8-126">Data type: string</span></span>  
  
 <span data-ttu-id="e2ac8-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e2ac8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e2ac8-128">El tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ac8-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2ac8-129">Requirements</span></span>  
  
|<span data-ttu-id="e2ac8-130">MOF</span><span class="sxs-lookup"><span data-stu-id="e2ac8-130">MOF</span></span>|<span data-ttu-id="e2ac8-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e2ac8-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e2ac8-132">Namespace</span></span>|<span data-ttu-id="e2ac8-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2ac8-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2ac8-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2ac8-134">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelBase>
