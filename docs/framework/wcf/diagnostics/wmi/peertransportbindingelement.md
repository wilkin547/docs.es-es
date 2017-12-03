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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 193000acf2f3c8a0eddb2552559ee40a0f5fced9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="d4cc1-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d4cc1-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="d4cc1-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="d4cc1-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4cc1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4cc1-104">Syntax</span></span>  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d4cc1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d4cc1-105">Methods</span></span>  
 <span data-ttu-id="d4cc1-106">La clase PeerTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="d4cc1-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d4cc1-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d4cc1-107">Properties</span></span>  
 <span data-ttu-id="d4cc1-108">La clase PeerTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="d4cc1-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="d4cc1-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="d4cc1-109">ListenIPAddress</span></span>  
 <span data-ttu-id="d4cc1-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d4cc1-110">Data type: string</span></span>  
  
 <span data-ttu-id="d4cc1-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d4cc1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4cc1-112">La dirección IP en la que el nodo del mismo nivel realiza escuchas para los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d4cc1-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="d4cc1-113">Puerto</span><span class="sxs-lookup"><span data-stu-id="d4cc1-113">Port</span></span>  
 <span data-ttu-id="d4cc1-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d4cc1-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="d4cc1-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d4cc1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4cc1-116">El puerto de la interfaz de red en el que este enlace procesa los mensajes del canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d4cc1-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="d4cc1-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d4cc1-117">Security</span></span>  
 <span data-ttu-id="d4cc1-118">Tipo de datos: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="d4cc1-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="d4cc1-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d4cc1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4cc1-120">Valores de seguridad de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d4cc1-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4cc1-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4cc1-121">Requirements</span></span>  
  
|<span data-ttu-id="d4cc1-122">MOF</span><span class="sxs-lookup"><span data-stu-id="d4cc1-122">MOF</span></span>|<span data-ttu-id="d4cc1-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d4cc1-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d4cc1-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d4cc1-124">Namespace</span></span>|<span data-ttu-id="d4cc1-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d4cc1-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4cc1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4cc1-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
