---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6af85d62fffada95537494692b8694f42d7a2932
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290093"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="5cc9a-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5cc9a-102">TcpTransportBindingElement</span></span>

<span data-ttu-id="5cc9a-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5cc9a-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc9a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cc9a-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5cc9a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5cc9a-105">Methods</span></span>  

 <span data-ttu-id="5cc9a-106">La clase TcpTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="5cc9a-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5cc9a-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5cc9a-107">Properties</span></span>  

 <span data-ttu-id="5cc9a-108">La clase TcpTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="5cc9a-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="5cc9a-109">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5cc9a-109">ConnectionPoolSettings</span></span>  

 <span data-ttu-id="5cc9a-110">Tipo de datos: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5cc9a-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="5cc9a-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5cc9a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5cc9a-112">Agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="5cc9a-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="5cc9a-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="5cc9a-113">ListenBacklog</span></span>  

 <span data-ttu-id="5cc9a-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="5cc9a-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="5cc9a-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5cc9a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5cc9a-116">El número máximo de solicitudes de conexión en cola que pueden estar pendientes.</span><span class="sxs-lookup"><span data-stu-id="5cc9a-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="5cc9a-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="5cc9a-117">PortSharingEnabled</span></span>  

 <span data-ttu-id="5cc9a-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="5cc9a-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="5cc9a-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5cc9a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5cc9a-120">Valor booleano que especifica si el uso compartido de los puertos TCP está habilitado para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="5cc9a-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="5cc9a-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="5cc9a-121">TeredoEnabled</span></span>  

 <span data-ttu-id="5cc9a-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="5cc9a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="5cc9a-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="5cc9a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5cc9a-124">Un valor booleano que especifica si Teredo (una tecnología para direccionar clientes que están detrás de firewalls) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="5cc9a-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc9a-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5cc9a-125">Requirements</span></span>  
  
|<span data-ttu-id="5cc9a-126">MOF</span><span class="sxs-lookup"><span data-stu-id="5cc9a-126">MOF</span></span>|<span data-ttu-id="5cc9a-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5cc9a-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5cc9a-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="5cc9a-128">Namespace</span></span>|<span data-ttu-id="5cc9a-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5cc9a-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5cc9a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cc9a-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
