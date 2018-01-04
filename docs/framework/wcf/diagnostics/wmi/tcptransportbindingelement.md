---
title: TcpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e230cbccee211fbda219000fbbd2cda5275776b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="62ec7-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="62ec7-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="62ec7-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="62ec7-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62ec7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62ec7-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="62ec7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="62ec7-105">Methods</span></span>  
 <span data-ttu-id="62ec7-106">La clase TcpTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="62ec7-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="62ec7-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="62ec7-107">Properties</span></span>  
 <span data-ttu-id="62ec7-108">La clase TcpTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="62ec7-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="62ec7-109">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="62ec7-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="62ec7-110">Tipo de datos: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="62ec7-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="62ec7-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="62ec7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62ec7-112">Agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="62ec7-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="62ec7-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="62ec7-113">ListenBacklog</span></span>  
 <span data-ttu-id="62ec7-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="62ec7-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="62ec7-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="62ec7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62ec7-116">El número máximo de solicitudes de conexión en cola que pueden estar pendientes.</span><span class="sxs-lookup"><span data-stu-id="62ec7-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="62ec7-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="62ec7-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="62ec7-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="62ec7-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="62ec7-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="62ec7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62ec7-120">Valor booleano que especifica si el uso compartido de los puertos TCP está habilitado para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="62ec7-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="62ec7-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="62ec7-121">TeredoEnabled</span></span>  
 <span data-ttu-id="62ec7-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="62ec7-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="62ec7-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="62ec7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="62ec7-124">Un valor booleano que especifica si Teredo (una tecnología para direccionar clientes que están detrás de firewalls) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="62ec7-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62ec7-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62ec7-125">Requirements</span></span>  
  
|<span data-ttu-id="62ec7-126">MOF</span><span class="sxs-lookup"><span data-stu-id="62ec7-126">MOF</span></span>|<span data-ttu-id="62ec7-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="62ec7-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="62ec7-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="62ec7-128">Namespace</span></span>|<span data-ttu-id="62ec7-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="62ec7-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62ec7-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="62ec7-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
