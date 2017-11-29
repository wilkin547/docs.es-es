---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48364c2bcfa50476ac5f9f00f87c17f97dc14017
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="69fd7-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="69fd7-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="69fd7-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="69fd7-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69fd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69fd7-104">Syntax</span></span>  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="69fd7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="69fd7-105">Methods</span></span>  
 <span data-ttu-id="69fd7-106">La clase PeerTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="69fd7-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="69fd7-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="69fd7-107">Properties</span></span>  
 <span data-ttu-id="69fd7-108">La clase PeerTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="69fd7-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="69fd7-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="69fd7-109">ListenIPAddress</span></span>  
 <span data-ttu-id="69fd7-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="69fd7-110">Data type: string</span></span>  
  
 <span data-ttu-id="69fd7-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="69fd7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="69fd7-112">La dirección IP en la que el nodo del mismo nivel realiza escuchas para los mensajes.</span><span class="sxs-lookup"><span data-stu-id="69fd7-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="69fd7-113">Puerto</span><span class="sxs-lookup"><span data-stu-id="69fd7-113">Port</span></span>  
 <span data-ttu-id="69fd7-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="69fd7-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="69fd7-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="69fd7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="69fd7-116">El puerto de la interfaz de red en el que este enlace procesa los mensajes del canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="69fd7-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="69fd7-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="69fd7-117">Security</span></span>  
 <span data-ttu-id="69fd7-118">Tipo de datos: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="69fd7-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="69fd7-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="69fd7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="69fd7-120">Valores de seguridad de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="69fd7-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69fd7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69fd7-121">Requirements</span></span>  
  
|<span data-ttu-id="69fd7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="69fd7-122">MOF</span></span>|<span data-ttu-id="69fd7-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="69fd7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="69fd7-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="69fd7-124">Namespace</span></span>|<span data-ttu-id="69fd7-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="69fd7-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69fd7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="69fd7-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
