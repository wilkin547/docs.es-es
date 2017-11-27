---
title: TcpConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5038d093333eca9ca191c3ecae4cfa889d723276
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="ed3f8-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ed3f8-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="ed3f8-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ed3f8-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed3f8-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ed3f8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ed3f8-105">Methods</span></span>  
 <span data-ttu-id="ed3f8-106">La clase TcpConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ed3f8-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ed3f8-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ed3f8-107">Properties</span></span>  
 <span data-ttu-id="ed3f8-108">La clase TcpConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="ed3f8-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="ed3f8-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="ed3f8-109">GroupName</span></span>  
 <span data-ttu-id="ed3f8-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ed3f8-110">Data type: string</span></span>  
  
 <span data-ttu-id="ed3f8-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ed3f8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed3f8-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="ed3f8-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="ed3f8-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="ed3f8-113">IdleTimeout</span></span>  
 <span data-ttu-id="ed3f8-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="ed3f8-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="ed3f8-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ed3f8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed3f8-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="ed3f8-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="ed3f8-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="ed3f8-117">LeaseTimeout</span></span>  
 <span data-ttu-id="ed3f8-118">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="ed3f8-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="ed3f8-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ed3f8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed3f8-120">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ed3f8-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="ed3f8-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ed3f8-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="ed3f8-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="ed3f8-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="ed3f8-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ed3f8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ed3f8-124">Las conexiones máximas salientes para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="ed3f8-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3f8-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed3f8-125">Requirements</span></span>  
  
|<span data-ttu-id="ed3f8-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ed3f8-126">MOF</span></span>|<span data-ttu-id="ed3f8-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ed3f8-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ed3f8-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ed3f8-128">Namespace</span></span>|<span data-ttu-id="ed3f8-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ed3f8-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed3f8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed3f8-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
