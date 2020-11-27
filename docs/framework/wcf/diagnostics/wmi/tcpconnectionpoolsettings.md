---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: de00cac851e4c6d0fd6df16f3a01b65bb5f43415
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294682"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="6c301-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="6c301-102">TcpConnectionPoolSettings</span></span>

<span data-ttu-id="6c301-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="6c301-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c301-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c301-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6c301-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6c301-105">Methods</span></span>  

 <span data-ttu-id="6c301-106">La clase TcpConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6c301-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6c301-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6c301-107">Properties</span></span>  

 <span data-ttu-id="6c301-108">La clase TcpConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="6c301-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="6c301-109">NombreDeGrupo</span><span class="sxs-lookup"><span data-stu-id="6c301-109">GroupName</span></span>  

 <span data-ttu-id="6c301-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="6c301-110">Data type: string</span></span>  
  
 <span data-ttu-id="6c301-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6c301-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c301-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="6c301-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="6c301-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="6c301-113">IdleTimeout</span></span>  

 <span data-ttu-id="6c301-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="6c301-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="6c301-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6c301-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c301-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="6c301-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="6c301-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="6c301-117">LeaseTimeout</span></span>  

 <span data-ttu-id="6c301-118">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="6c301-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="6c301-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6c301-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c301-120">El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6c301-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="6c301-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="6c301-121">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="6c301-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="6c301-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="6c301-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6c301-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6c301-124">Las conexiones máximas salientes para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6c301-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c301-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c301-125">Requirements</span></span>  
  
|<span data-ttu-id="6c301-126">MOF</span><span class="sxs-lookup"><span data-stu-id="6c301-126">MOF</span></span>|<span data-ttu-id="6c301-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6c301-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6c301-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6c301-128">Namespace</span></span>|<span data-ttu-id="6c301-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6c301-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c301-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c301-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
