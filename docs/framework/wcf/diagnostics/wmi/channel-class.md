---
description: 'Más información sobre: clase de canal'
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: dcc92f78f09e9a73a24134c6c0685949f46f38dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757727"
---
# <a name="channel-class"></a><span data-ttu-id="4d7cf-103">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="4d7cf-103">Channel class</span></span>

<span data-ttu-id="4d7cf-104">Canal</span><span class="sxs-lookup"><span data-stu-id="4d7cf-104">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d7cf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d7cf-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="4d7cf-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d7cf-106">Methods</span></span>  

 <span data-ttu-id="4d7cf-107">La clase Canal no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-107">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4d7cf-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4d7cf-108">Properties</span></span>  

 <span data-ttu-id="4d7cf-109">La clase Canal tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-109">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="4d7cf-110">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="4d7cf-110">LocalAddress</span></span>  

 <span data-ttu-id="4d7cf-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4d7cf-111">Data type: string</span></span>  
  
 <span data-ttu-id="4d7cf-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4d7cf-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d7cf-113">punto de conexión local para el canal.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-113">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="4d7cf-114">ref</span><span class="sxs-lookup"><span data-stu-id="4d7cf-114">ref</span></span>  

 <span data-ttu-id="4d7cf-115">Tipo de datos: punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4d7cf-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="4d7cf-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4d7cf-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d7cf-117">Una referencia al extremo al que se conecta el canal.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-117">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="4d7cf-118">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="4d7cf-118">RemoteAddress</span></span>  

 <span data-ttu-id="4d7cf-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4d7cf-119">Data type: string</span></span>  
  
 <span data-ttu-id="4d7cf-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4d7cf-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d7cf-121">Dirección remota asociada al canal.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-121">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="4d7cf-122">SessionId</span><span class="sxs-lookup"><span data-stu-id="4d7cf-122">SessionId</span></span>  

 <span data-ttu-id="4d7cf-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4d7cf-123">Data type: string</span></span>  
  
 <span data-ttu-id="4d7cf-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4d7cf-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d7cf-125">Identificador de la sesión actual, si lo hubiera.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-125">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="4d7cf-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="4d7cf-126">Type</span></span>  

 <span data-ttu-id="4d7cf-127">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4d7cf-127">Data type: string</span></span>  
  
 <span data-ttu-id="4d7cf-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4d7cf-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d7cf-129">El tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-129">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d7cf-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d7cf-130">Requirements</span></span>  
  
|<span data-ttu-id="4d7cf-131">MOF</span><span class="sxs-lookup"><span data-stu-id="4d7cf-131">MOF</span></span>|<span data-ttu-id="4d7cf-132">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4d7cf-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4d7cf-133">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4d7cf-133">Namespace</span></span>|<span data-ttu-id="4d7cf-134">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4d7cf-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d7cf-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d7cf-135">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
