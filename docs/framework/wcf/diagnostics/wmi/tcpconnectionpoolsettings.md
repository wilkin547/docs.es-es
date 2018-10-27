---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: f9e1c043579f632f16a7cf36bf34c2467a743e47
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50189568"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="ad5cc-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ad5cc-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="ad5cc-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="ad5cc-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad5cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad5cc-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ad5cc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ad5cc-105">Methods</span></span>  
 <span data-ttu-id="ad5cc-106">La clase TcpConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ad5cc-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ad5cc-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ad5cc-107">Properties</span></span>  
 <span data-ttu-id="ad5cc-108">La clase TcpConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="ad5cc-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="ad5cc-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="ad5cc-109">GroupName</span></span>  
 <span data-ttu-id="ad5cc-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ad5cc-110">Data type: string</span></span>  
  
 <span data-ttu-id="ad5cc-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ad5cc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad5cc-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="ad5cc-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="ad5cc-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="ad5cc-113">IdleTimeout</span></span>  
 <span data-ttu-id="ad5cc-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="ad5cc-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="ad5cc-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ad5cc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad5cc-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="ad5cc-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="ad5cc-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="ad5cc-117">LeaseTimeout</span></span>  
 <span data-ttu-id="ad5cc-118">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="ad5cc-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="ad5cc-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ad5cc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad5cc-120">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ad5cc-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="ad5cc-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ad5cc-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="ad5cc-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="ad5cc-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="ad5cc-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ad5cc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad5cc-124">Las conexiones máximas salientes para cada extremo.</span><span class="sxs-lookup"><span data-stu-id="ad5cc-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad5cc-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad5cc-125">Requirements</span></span>  
  
|<span data-ttu-id="ad5cc-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ad5cc-126">MOF</span></span>|<span data-ttu-id="ad5cc-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ad5cc-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad5cc-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ad5cc-128">Namespace</span></span>|<span data-ttu-id="ad5cc-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ad5cc-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad5cc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad5cc-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
