---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8c2d4bfc08a503a8d6eb0e8abf6f1e798b90bc83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963220"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="fb48f-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fb48f-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="fb48f-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fb48f-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb48f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb48f-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fb48f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fb48f-105">Methods</span></span>  
 <span data-ttu-id="fb48f-106">La clase NamedPipeConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fb48f-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fb48f-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fb48f-107">Properties</span></span>  
 <span data-ttu-id="fb48f-108">La clase NamedPipeConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="fb48f-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="fb48f-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="fb48f-109">GroupName</span></span>  
 <span data-ttu-id="fb48f-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fb48f-110">Data type: string</span></span>  
  
 <span data-ttu-id="fb48f-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fb48f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb48f-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="fb48f-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="fb48f-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="fb48f-113">IdleTimeout</span></span>  
 <span data-ttu-id="fb48f-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="fb48f-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="fb48f-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fb48f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb48f-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="fb48f-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="fb48f-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="fb48f-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="fb48f-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fb48f-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="fb48f-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fb48f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb48f-120">El número máximo de conexiones salientes para cada punto de conexión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="fb48f-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb48f-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb48f-121">Requirements</span></span>  
  
|<span data-ttu-id="fb48f-122">MOF</span><span class="sxs-lookup"><span data-stu-id="fb48f-122">MOF</span></span>|<span data-ttu-id="fb48f-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fb48f-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fb48f-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fb48f-124">Namespace</span></span>|<span data-ttu-id="fb48f-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fb48f-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb48f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb48f-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
