---
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: a920636e7df9609b12834366b1488c80122f9fca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274236"
---
# <a name="channel-class"></a><span data-ttu-id="dc628-102">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="dc628-102">Channel class</span></span>

<span data-ttu-id="dc628-103">Canal</span><span class="sxs-lookup"><span data-stu-id="dc628-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc628-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc628-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="dc628-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dc628-105">Methods</span></span>  

 <span data-ttu-id="dc628-106">La clase Canal no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="dc628-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dc628-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="dc628-107">Properties</span></span>  

 <span data-ttu-id="dc628-108">La clase Canal tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="dc628-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="dc628-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="dc628-109">LocalAddress</span></span>  

 <span data-ttu-id="dc628-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="dc628-110">Data type: string</span></span>  
  
 <span data-ttu-id="dc628-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="dc628-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc628-112">punto de conexión local para el canal.</span><span class="sxs-lookup"><span data-stu-id="dc628-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="dc628-113">ref</span><span class="sxs-lookup"><span data-stu-id="dc628-113">ref</span></span>  

 <span data-ttu-id="dc628-114">Tipo de datos: punto de conexión</span><span class="sxs-lookup"><span data-stu-id="dc628-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="dc628-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="dc628-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc628-116">Una referencia al extremo al que se conecta el canal.</span><span class="sxs-lookup"><span data-stu-id="dc628-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="dc628-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="dc628-117">RemoteAddress</span></span>  

 <span data-ttu-id="dc628-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="dc628-118">Data type: string</span></span>  
  
 <span data-ttu-id="dc628-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="dc628-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc628-120">Dirección remota asociada al canal.</span><span class="sxs-lookup"><span data-stu-id="dc628-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="dc628-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="dc628-121">SessionId</span></span>  

 <span data-ttu-id="dc628-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="dc628-122">Data type: string</span></span>  
  
 <span data-ttu-id="dc628-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="dc628-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc628-124">Identificador de la sesión actual, si lo hubiera.</span><span class="sxs-lookup"><span data-stu-id="dc628-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="dc628-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="dc628-125">Type</span></span>  

 <span data-ttu-id="dc628-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="dc628-126">Data type: string</span></span>  
  
 <span data-ttu-id="dc628-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="dc628-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc628-128">El tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="dc628-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc628-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc628-129">Requirements</span></span>  
  
|<span data-ttu-id="dc628-130">MOF</span><span class="sxs-lookup"><span data-stu-id="dc628-130">MOF</span></span>|<span data-ttu-id="dc628-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dc628-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dc628-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="dc628-132">Namespace</span></span>|<span data-ttu-id="dc628-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc628-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc628-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc628-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
