---
title: NamedPipeConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cf9c39334289cb30d1a01917c0be37da02fcdc5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="e94b6-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e94b6-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="e94b6-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e94b6-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e94b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e94b6-104">Syntax</span></span>  
  
```  
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e94b6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e94b6-105">Methods</span></span>  
 <span data-ttu-id="e94b6-106">La clase NamedPipeConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e94b6-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e94b6-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e94b6-107">Properties</span></span>  
 <span data-ttu-id="e94b6-108">La clase NamedPipeConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="e94b6-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="e94b6-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="e94b6-109">GroupName</span></span>  
 <span data-ttu-id="e94b6-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e94b6-110">Data type: string</span></span>  
  
 <span data-ttu-id="e94b6-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e94b6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e94b6-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="e94b6-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="e94b6-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="e94b6-113">IdleTimeout</span></span>  
 <span data-ttu-id="e94b6-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="e94b6-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="e94b6-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e94b6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e94b6-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="e94b6-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="e94b6-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e94b6-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="e94b6-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="e94b6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="e94b6-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e94b6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e94b6-120">El número máximo de conexiones salientes para cada extremo en el cliente.</span><span class="sxs-lookup"><span data-stu-id="e94b6-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e94b6-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e94b6-121">Requirements</span></span>  
  
|<span data-ttu-id="e94b6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e94b6-122">MOF</span></span>|<span data-ttu-id="e94b6-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e94b6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e94b6-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e94b6-124">Namespace</span></span>|<span data-ttu-id="e94b6-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e94b6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e94b6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e94b6-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
