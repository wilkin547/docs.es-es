---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 6fa68eed241edaea40b66c31240a4201e05779f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093534"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="2b6af-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="2b6af-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="2b6af-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="2b6af-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b6af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b6af-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2b6af-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2b6af-105">Methods</span></span>  
 <span data-ttu-id="2b6af-106">La clase TcpConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="2b6af-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2b6af-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2b6af-107">Properties</span></span>  
 <span data-ttu-id="2b6af-108">La clase TcpConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2b6af-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="2b6af-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="2b6af-109">GroupName</span></span>  
 <span data-ttu-id="2b6af-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2b6af-110">Data type: string</span></span>  
  
 <span data-ttu-id="2b6af-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2b6af-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b6af-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="2b6af-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="2b6af-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="2b6af-113">IdleTimeout</span></span>  
 <span data-ttu-id="2b6af-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="2b6af-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="2b6af-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2b6af-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b6af-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="2b6af-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="2b6af-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="2b6af-117">LeaseTimeout</span></span>  
 <span data-ttu-id="2b6af-118">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="2b6af-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="2b6af-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2b6af-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b6af-120">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2b6af-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="2b6af-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="2b6af-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="2b6af-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="2b6af-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="2b6af-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2b6af-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b6af-124">Las conexiones máximas salientes para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2b6af-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b6af-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b6af-125">Requirements</span></span>  
  
|<span data-ttu-id="2b6af-126">MOF</span><span class="sxs-lookup"><span data-stu-id="2b6af-126">MOF</span></span>|<span data-ttu-id="2b6af-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2b6af-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2b6af-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="2b6af-128">Namespace</span></span>|<span data-ttu-id="2b6af-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2b6af-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b6af-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b6af-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
