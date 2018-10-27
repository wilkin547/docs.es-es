---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 58bf07b0429ca2435b5aae3683ef69951a10003e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185188"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="9779e-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9779e-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="9779e-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9779e-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9779e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9779e-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9779e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9779e-105">Methods</span></span>  
 <span data-ttu-id="9779e-106">La clase PeerTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="9779e-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9779e-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9779e-107">Properties</span></span>  
 <span data-ttu-id="9779e-108">La clase PeerTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="9779e-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="9779e-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="9779e-109">ListenIPAddress</span></span>  
 <span data-ttu-id="9779e-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9779e-110">Data type: string</span></span>  
  
 <span data-ttu-id="9779e-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9779e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9779e-112">La dirección IP en la que el nodo del mismo nivel realiza escuchas para los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9779e-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="9779e-113">Puerto</span><span class="sxs-lookup"><span data-stu-id="9779e-113">Port</span></span>  
 <span data-ttu-id="9779e-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="9779e-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="9779e-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9779e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9779e-116">El puerto de la interfaz de red en el que este enlace procesa los mensajes del canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="9779e-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="9779e-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9779e-117">Security</span></span>  
 <span data-ttu-id="9779e-118">Tipo de datos: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9779e-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="9779e-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9779e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9779e-120">Valores de seguridad de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="9779e-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9779e-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9779e-121">Requirements</span></span>  
  
|<span data-ttu-id="9779e-122">MOF</span><span class="sxs-lookup"><span data-stu-id="9779e-122">MOF</span></span>|<span data-ttu-id="9779e-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9779e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9779e-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9779e-124">Namespace</span></span>|<span data-ttu-id="9779e-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9779e-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9779e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9779e-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
