---
description: 'Más información acerca de: PeerTransportBindingElement'
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: b1ca8020f51a5f9b121f7d238d82b9971d13cdd4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757337"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="09931-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="09931-103">PeerTransportBindingElement</span></span>

<span data-ttu-id="09931-104">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="09931-104">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09931-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09931-105">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="09931-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="09931-106">Methods</span></span>  

 <span data-ttu-id="09931-107">La clase PeerTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="09931-107">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="09931-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="09931-108">Properties</span></span>  

 <span data-ttu-id="09931-109">La clase PeerTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="09931-109">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="09931-110">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="09931-110">ListenIPAddress</span></span>  

 <span data-ttu-id="09931-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="09931-111">Data type: string</span></span>  
  
 <span data-ttu-id="09931-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="09931-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09931-113">La dirección IP en la que el nodo del mismo nivel realiza escuchas para los mensajes.</span><span class="sxs-lookup"><span data-stu-id="09931-113">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="09931-114">Puerto</span><span class="sxs-lookup"><span data-stu-id="09931-114">Port</span></span>  

 <span data-ttu-id="09931-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="09931-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="09931-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="09931-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09931-117">El puerto de la interfaz de red en el que este enlace procesa los mensajes del canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="09931-117">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="09931-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="09931-118">Security</span></span>  

 <span data-ttu-id="09931-119">Tipo de datos: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="09931-119">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="09931-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="09931-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09931-121">Valores de seguridad de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="09931-121">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09931-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09931-122">Requirements</span></span>  
  
|<span data-ttu-id="09931-123">MOF</span><span class="sxs-lookup"><span data-stu-id="09931-123">MOF</span></span>|<span data-ttu-id="09931-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="09931-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="09931-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="09931-125">Namespace</span></span>|<span data-ttu-id="09931-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="09931-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09931-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="09931-127">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
