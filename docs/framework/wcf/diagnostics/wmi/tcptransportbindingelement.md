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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 180e954661319cb32edfd3180418fe9b1571ea5c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="e7231-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e7231-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="e7231-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e7231-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7231-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7231-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e7231-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e7231-105">Methods</span></span>  
 <span data-ttu-id="e7231-106">La clase TcpTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e7231-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e7231-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e7231-107">Properties</span></span>  
 <span data-ttu-id="e7231-108">La clase TcpTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7231-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="e7231-109">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e7231-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="e7231-110">Tipo de datos: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e7231-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="e7231-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e7231-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7231-112">Agrupación de conexiones.</span><span class="sxs-lookup"><span data-stu-id="e7231-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="e7231-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="e7231-113">ListenBacklog</span></span>  
 <span data-ttu-id="e7231-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="e7231-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="e7231-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e7231-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7231-116">El número máximo de solicitudes de conexión en cola que pueden estar pendientes.</span><span class="sxs-lookup"><span data-stu-id="e7231-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="e7231-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="e7231-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="e7231-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e7231-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="e7231-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e7231-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7231-120">Valor booleano que especifica si el uso compartido de los puertos TCP está habilitado para esta conexión.</span><span class="sxs-lookup"><span data-stu-id="e7231-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="e7231-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="e7231-121">TeredoEnabled</span></span>  
 <span data-ttu-id="e7231-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e7231-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e7231-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e7231-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7231-124">Un valor booleano que especifica si Teredo (una tecnología para direccionar clientes que están detrás de firewalls) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e7231-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7231-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7231-125">Requirements</span></span>  
  
|<span data-ttu-id="e7231-126">MOF</span><span class="sxs-lookup"><span data-stu-id="e7231-126">MOF</span></span>|<span data-ttu-id="e7231-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e7231-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e7231-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e7231-128">Namespace</span></span>|<span data-ttu-id="e7231-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e7231-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7231-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7231-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
