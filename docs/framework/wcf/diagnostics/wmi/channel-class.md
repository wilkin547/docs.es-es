---
title: Clase de canal
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1df634a61cce695fca74fdfe53beea6c0f83d082
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="channel-class"></a><span data-ttu-id="2e365-102">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="2e365-102">Channel class</span></span>
<span data-ttu-id="2e365-103">Canal</span><span class="sxs-lookup"><span data-stu-id="2e365-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e365-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e365-104">Syntax</span></span>  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2e365-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2e365-105">Methods</span></span>  
 <span data-ttu-id="2e365-106">La clase Canal no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="2e365-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2e365-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2e365-107">Properties</span></span>  
 <span data-ttu-id="2e365-108">La clase Canal tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="2e365-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="2e365-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="2e365-109">LocalAddress</span></span>  
 <span data-ttu-id="2e365-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2e365-110">Data type: string</span></span>  
  
 <span data-ttu-id="2e365-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e365-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e365-112">Extremo local para el canal.</span><span class="sxs-lookup"><span data-stu-id="2e365-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="2e365-113">ref</span><span class="sxs-lookup"><span data-stu-id="2e365-113">ref</span></span>  
 <span data-ttu-id="2e365-114">Tipo de datos: extremo</span><span class="sxs-lookup"><span data-stu-id="2e365-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="2e365-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e365-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e365-116">Una referencia al extremo al que se conecta el canal.</span><span class="sxs-lookup"><span data-stu-id="2e365-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="2e365-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="2e365-117">RemoteAddress</span></span>  
 <span data-ttu-id="2e365-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2e365-118">Data type: string</span></span>  
  
 <span data-ttu-id="2e365-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e365-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e365-120">Dirección remota asociada al canal.</span><span class="sxs-lookup"><span data-stu-id="2e365-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="2e365-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="2e365-121">SessionId</span></span>  
 <span data-ttu-id="2e365-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2e365-122">Data type: string</span></span>  
  
 <span data-ttu-id="2e365-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e365-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e365-124">Identificador de la sesión actual, si lo hubiera.</span><span class="sxs-lookup"><span data-stu-id="2e365-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="2e365-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="2e365-125">Type</span></span>  
 <span data-ttu-id="2e365-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2e365-126">Data type: string</span></span>  
  
 <span data-ttu-id="2e365-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e365-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e365-128">El tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="2e365-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e365-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e365-129">Requirements</span></span>  
  
|<span data-ttu-id="2e365-130">MOF</span><span class="sxs-lookup"><span data-stu-id="2e365-130">MOF</span></span>|<span data-ttu-id="2e365-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2e365-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2e365-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="2e365-132">Namespace</span></span>|<span data-ttu-id="2e365-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2e365-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e365-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e365-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
