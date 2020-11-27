---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ae6a3448896cb206bce8867daf7104c3e484ecc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269020"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="ca778-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ca778-102">PeerTransportBindingElement</span></span>

<span data-ttu-id="ca778-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ca778-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca778-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca778-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ca778-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ca778-105">Methods</span></span>  

 <span data-ttu-id="ca778-106">La clase PeerTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ca778-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ca778-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ca778-107">Properties</span></span>  

 <span data-ttu-id="ca778-108">La clase PeerTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="ca778-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="ca778-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="ca778-109">ListenIPAddress</span></span>  

 <span data-ttu-id="ca778-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ca778-110">Data type: string</span></span>  
  
 <span data-ttu-id="ca778-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ca778-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca778-112">La dirección IP en la que el nodo del mismo nivel realiza escuchas para los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ca778-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="ca778-113">Port</span><span class="sxs-lookup"><span data-stu-id="ca778-113">Port</span></span>  

 <span data-ttu-id="ca778-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="ca778-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="ca778-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ca778-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca778-116">El puerto de la interfaz de red en el que este enlace procesa los mensajes del canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="ca778-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="ca778-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ca778-117">Security</span></span>  

 <span data-ttu-id="ca778-118">Tipo de datos: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ca778-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="ca778-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ca778-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ca778-120">Valores de seguridad de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="ca778-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca778-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca778-121">Requirements</span></span>  
  
|<span data-ttu-id="ca778-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ca778-122">MOF</span></span>|<span data-ttu-id="ca778-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ca778-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ca778-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ca778-124">Namespace</span></span>|<span data-ttu-id="ca778-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ca778-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca778-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca778-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
