---
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 108d5f8e3cd092863dbd48e2bb9d180798b091a4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197878"
---
# <a name="channel-class"></a><span data-ttu-id="6e7ae-102">Clase de canal</span><span class="sxs-lookup"><span data-stu-id="6e7ae-102">Channel class</span></span>
<span data-ttu-id="6e7ae-103">Canal</span><span class="sxs-lookup"><span data-stu-id="6e7ae-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e7ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e7ae-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="6e7ae-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6e7ae-105">Methods</span></span>  
 <span data-ttu-id="6e7ae-106">La clase Canal no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6e7ae-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6e7ae-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6e7ae-107">Properties</span></span>  
 <span data-ttu-id="6e7ae-108">La clase Canal tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="6e7ae-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="6e7ae-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="6e7ae-109">LocalAddress</span></span>  
 <span data-ttu-id="6e7ae-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6e7ae-110">Data type: string</span></span>  
  
 <span data-ttu-id="6e7ae-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6e7ae-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e7ae-112">Extremo local para el canal.</span><span class="sxs-lookup"><span data-stu-id="6e7ae-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6e7ae-113">ref</span><span class="sxs-lookup"><span data-stu-id="6e7ae-113">ref</span></span>  
 <span data-ttu-id="6e7ae-114">Tipo de datos: extremo</span><span class="sxs-lookup"><span data-stu-id="6e7ae-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="6e7ae-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6e7ae-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e7ae-116">Una referencia al extremo al que se conecta el canal.</span><span class="sxs-lookup"><span data-stu-id="6e7ae-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="6e7ae-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="6e7ae-117">RemoteAddress</span></span>  
 <span data-ttu-id="6e7ae-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6e7ae-118">Data type: string</span></span>  
  
 <span data-ttu-id="6e7ae-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6e7ae-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e7ae-120">Dirección remota asociada al canal.</span><span class="sxs-lookup"><span data-stu-id="6e7ae-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="6e7ae-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="6e7ae-121">SessionId</span></span>  
 <span data-ttu-id="6e7ae-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6e7ae-122">Data type: string</span></span>  
  
 <span data-ttu-id="6e7ae-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6e7ae-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e7ae-124">Identificador de la sesión actual, si lo hubiera.</span><span class="sxs-lookup"><span data-stu-id="6e7ae-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="6e7ae-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="6e7ae-125">Type</span></span>  
 <span data-ttu-id="6e7ae-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6e7ae-126">Data type: string</span></span>  
  
 <span data-ttu-id="6e7ae-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6e7ae-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6e7ae-128">El tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="6e7ae-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e7ae-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e7ae-129">Requirements</span></span>  
  
|<span data-ttu-id="6e7ae-130">MOF</span><span class="sxs-lookup"><span data-stu-id="6e7ae-130">MOF</span></span>|<span data-ttu-id="6e7ae-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6e7ae-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6e7ae-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6e7ae-132">Namespace</span></span>|<span data-ttu-id="6e7ae-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6e7ae-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e7ae-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e7ae-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
