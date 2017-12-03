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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eaec1b7d179810faaba016cfa0c5eb7e6c950ab6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="b4697-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b4697-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="b4697-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b4697-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4697-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4697-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b4697-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b4697-105">Methods</span></span>  
 <span data-ttu-id="b4697-106">La clase TcpConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b4697-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b4697-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b4697-107">Properties</span></span>  
 <span data-ttu-id="b4697-108">La clase TcpConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b4697-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="b4697-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="b4697-109">GroupName</span></span>  
 <span data-ttu-id="b4697-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b4697-110">Data type: string</span></span>  
  
 <span data-ttu-id="b4697-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4697-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4697-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="b4697-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="b4697-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="b4697-113">IdleTimeout</span></span>  
 <span data-ttu-id="b4697-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="b4697-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="b4697-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4697-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4697-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="b4697-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="b4697-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="b4697-117">LeaseTimeout</span></span>  
 <span data-ttu-id="b4697-118">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="b4697-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="b4697-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4697-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4697-120">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b4697-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="b4697-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b4697-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="b4697-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="b4697-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="b4697-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b4697-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b4697-124">Las conexiones máximas salientes para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="b4697-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4697-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4697-125">Requirements</span></span>  
  
|<span data-ttu-id="b4697-126">MOF</span><span class="sxs-lookup"><span data-stu-id="b4697-126">MOF</span></span>|<span data-ttu-id="b4697-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b4697-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b4697-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b4697-128">Namespace</span></span>|<span data-ttu-id="b4697-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b4697-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4697-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4697-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
