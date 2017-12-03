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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93632d6a178c0f58143fc148a0e1eb51be94ed17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="channel-class"></a><span data-ttu-id="9f5eb-102">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="9f5eb-102">Channel class</span></span>
<span data-ttu-id="9f5eb-103">Canal</span><span class="sxs-lookup"><span data-stu-id="9f5eb-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f5eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f5eb-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9f5eb-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9f5eb-105">Methods</span></span>  
 <span data-ttu-id="9f5eb-106">La clase Canal no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9f5eb-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9f5eb-107">Properties</span></span>  
 <span data-ttu-id="9f5eb-108">La clase Canal tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="9f5eb-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="9f5eb-109">LocalAddress</span></span>  
 <span data-ttu-id="9f5eb-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9f5eb-110">Data type: string</span></span>  
  
 <span data-ttu-id="9f5eb-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f5eb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f5eb-112">Extremo local para el canal.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9f5eb-113">ref</span><span class="sxs-lookup"><span data-stu-id="9f5eb-113">ref</span></span>  
 <span data-ttu-id="9f5eb-114">Tipo de datos: extremo</span><span class="sxs-lookup"><span data-stu-id="9f5eb-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="9f5eb-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f5eb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f5eb-116">Una referencia al extremo al que se conecta el canal.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="9f5eb-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="9f5eb-117">RemoteAddress</span></span>  
 <span data-ttu-id="9f5eb-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9f5eb-118">Data type: string</span></span>  
  
 <span data-ttu-id="9f5eb-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f5eb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f5eb-120">Dirección remota asociada al canal.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="9f5eb-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="9f5eb-121">SessionId</span></span>  
 <span data-ttu-id="9f5eb-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9f5eb-122">Data type: string</span></span>  
  
 <span data-ttu-id="9f5eb-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f5eb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f5eb-124">Identificador de la sesión actual, si lo hubiera.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="9f5eb-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="9f5eb-125">Type</span></span>  
 <span data-ttu-id="9f5eb-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9f5eb-126">Data type: string</span></span>  
  
 <span data-ttu-id="9f5eb-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f5eb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f5eb-128">El tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f5eb-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f5eb-129">Requirements</span></span>  
  
|<span data-ttu-id="9f5eb-130">MOF</span><span class="sxs-lookup"><span data-stu-id="9f5eb-130">MOF</span></span>|<span data-ttu-id="9f5eb-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9f5eb-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9f5eb-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9f5eb-132">Namespace</span></span>|<span data-ttu-id="9f5eb-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9f5eb-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f5eb-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f5eb-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
