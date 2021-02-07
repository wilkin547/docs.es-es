---
description: 'Más información acerca de: TcpConnectionPoolSettings'
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 927fcba7f94bcbfa80e06479e79bf20986a661e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715202"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="c13a9-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c13a9-103">TcpConnectionPoolSettings</span></span>

<span data-ttu-id="c13a9-104">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="c13a9-104">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c13a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c13a9-105">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c13a9-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="c13a9-106">Methods</span></span>  

 <span data-ttu-id="c13a9-107">La clase TcpConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="c13a9-107">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c13a9-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c13a9-108">Properties</span></span>  

 <span data-ttu-id="c13a9-109">La clase TcpConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c13a9-109">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="c13a9-110">NombreDeGrupo</span><span class="sxs-lookup"><span data-stu-id="c13a9-110">GroupName</span></span>  

 <span data-ttu-id="c13a9-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c13a9-111">Data type: string</span></span>  
  
 <span data-ttu-id="c13a9-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c13a9-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c13a9-113">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="c13a9-113">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="c13a9-114">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="c13a9-114">IdleTimeout</span></span>  

 <span data-ttu-id="c13a9-115">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="c13a9-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="c13a9-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c13a9-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c13a9-117">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="c13a9-117">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="c13a9-118">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="c13a9-118">LeaseTimeout</span></span>  

 <span data-ttu-id="c13a9-119">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="c13a9-119">Data type: datetime</span></span>  
  
 <span data-ttu-id="c13a9-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c13a9-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c13a9-121">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c13a9-121">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="c13a9-122">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c13a9-122">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="c13a9-123">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c13a9-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="c13a9-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c13a9-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c13a9-125">Las conexiones máximas salientes para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="c13a9-125">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c13a9-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c13a9-126">Requirements</span></span>  
  
|<span data-ttu-id="c13a9-127">MOF</span><span class="sxs-lookup"><span data-stu-id="c13a9-127">MOF</span></span>|<span data-ttu-id="c13a9-128">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c13a9-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c13a9-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c13a9-129">Namespace</span></span>|<span data-ttu-id="c13a9-130">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c13a9-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c13a9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c13a9-131">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
