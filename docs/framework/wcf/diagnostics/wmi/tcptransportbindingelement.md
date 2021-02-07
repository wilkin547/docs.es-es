---
description: 'Más información acerca de: TcpTransportBindingElement'
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: b52bb2eb4b40648808459f76e068a6f72f9476a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715150"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="f73fb-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f73fb-103">TcpTransportBindingElement</span></span>

<span data-ttu-id="f73fb-104">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f73fb-104">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f73fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f73fb-105">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f73fb-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="f73fb-106">Methods</span></span>  

 <span data-ttu-id="f73fb-107">La clase TcpTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f73fb-107">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f73fb-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f73fb-108">Properties</span></span>  

 <span data-ttu-id="f73fb-109">La clase TcpTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="f73fb-109">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="f73fb-110">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f73fb-110">ConnectionPoolSettings</span></span>  

 <span data-ttu-id="f73fb-111">Tipo de datos: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f73fb-111">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="f73fb-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f73fb-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f73fb-113">Agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="f73fb-113">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="f73fb-114">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="f73fb-114">ListenBacklog</span></span>  

 <span data-ttu-id="f73fb-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f73fb-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="f73fb-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f73fb-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f73fb-117">El número máximo de solicitudes de conexión en cola que pueden estar pendientes.</span><span class="sxs-lookup"><span data-stu-id="f73fb-117">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="f73fb-118">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="f73fb-118">PortSharingEnabled</span></span>  

 <span data-ttu-id="f73fb-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f73fb-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="f73fb-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f73fb-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f73fb-121">Valor booleano que especifica si el uso compartido de los puertos TCP está habilitado para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="f73fb-121">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="f73fb-122">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="f73fb-122">TeredoEnabled</span></span>  

 <span data-ttu-id="f73fb-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f73fb-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="f73fb-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f73fb-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f73fb-125">Un valor booleano que especifica si Teredo (una tecnología para direccionar clientes que están detrás de firewalls) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="f73fb-125">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f73fb-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f73fb-126">Requirements</span></span>  
  
|<span data-ttu-id="f73fb-127">MOF</span><span class="sxs-lookup"><span data-stu-id="f73fb-127">MOF</span></span>|<span data-ttu-id="f73fb-128">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f73fb-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f73fb-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f73fb-129">Namespace</span></span>|<span data-ttu-id="f73fb-130">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f73fb-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f73fb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f73fb-131">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
