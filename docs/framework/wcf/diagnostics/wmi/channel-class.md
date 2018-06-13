---
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 4b7c66560c0c136a258c527d8a681d491eb50aae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485829"
---
# <a name="channel-class"></a><span data-ttu-id="c0bb1-102">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="c0bb1-102">Channel class</span></span>
<span data-ttu-id="c0bb1-103">Canal</span><span class="sxs-lookup"><span data-stu-id="c0bb1-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0bb1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0bb1-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c0bb1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c0bb1-105">Methods</span></span>  
 <span data-ttu-id="c0bb1-106">La clase Canal no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c0bb1-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c0bb1-107">Properties</span></span>  
 <span data-ttu-id="c0bb1-108">La clase Canal tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="c0bb1-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="c0bb1-109">LocalAddress</span></span>  
 <span data-ttu-id="c0bb1-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c0bb1-110">Data type: string</span></span>  
  
 <span data-ttu-id="c0bb1-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c0bb1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0bb1-112">Extremo local para el canal.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c0bb1-113">ref</span><span class="sxs-lookup"><span data-stu-id="c0bb1-113">ref</span></span>  
 <span data-ttu-id="c0bb1-114">Tipo de datos: extremo</span><span class="sxs-lookup"><span data-stu-id="c0bb1-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="c0bb1-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c0bb1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0bb1-116">Una referencia al extremo al que se conecta el canal.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="c0bb1-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="c0bb1-117">RemoteAddress</span></span>  
 <span data-ttu-id="c0bb1-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c0bb1-118">Data type: string</span></span>  
  
 <span data-ttu-id="c0bb1-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c0bb1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0bb1-120">Dirección remota asociada al canal.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="c0bb1-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="c0bb1-121">SessionId</span></span>  
 <span data-ttu-id="c0bb1-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c0bb1-122">Data type: string</span></span>  
  
 <span data-ttu-id="c0bb1-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c0bb1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0bb1-124">Identificador de la sesión actual, si lo hubiera.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="c0bb1-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="c0bb1-125">Type</span></span>  
 <span data-ttu-id="c0bb1-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c0bb1-126">Data type: string</span></span>  
  
 <span data-ttu-id="c0bb1-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c0bb1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0bb1-128">El tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0bb1-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0bb1-129">Requirements</span></span>  
  
|<span data-ttu-id="c0bb1-130">MOF</span><span class="sxs-lookup"><span data-stu-id="c0bb1-130">MOF</span></span>|<span data-ttu-id="c0bb1-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c0bb1-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c0bb1-132">Namespace</span></span>|<span data-ttu-id="c0bb1-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c0bb1-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0bb1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0bb1-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
