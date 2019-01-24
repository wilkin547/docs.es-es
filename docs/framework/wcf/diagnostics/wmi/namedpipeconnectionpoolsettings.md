---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 3dddfa878e3cb5bd89fb76009d0dba530debb297
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725082"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="1449f-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1449f-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="1449f-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1449f-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1449f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1449f-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1449f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1449f-105">Methods</span></span>  
 <span data-ttu-id="1449f-106">La clase NamedPipeConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1449f-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1449f-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1449f-107">Properties</span></span>  
 <span data-ttu-id="1449f-108">La clase NamedPipeConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1449f-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="1449f-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="1449f-109">GroupName</span></span>  
 <span data-ttu-id="1449f-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1449f-110">Data type: string</span></span>  
  
 <span data-ttu-id="1449f-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1449f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1449f-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="1449f-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="1449f-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="1449f-113">IdleTimeout</span></span>  
 <span data-ttu-id="1449f-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="1449f-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="1449f-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1449f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1449f-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="1449f-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="1449f-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="1449f-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="1449f-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="1449f-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="1449f-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1449f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1449f-120">El número máximo de conexiones salientes para cada punto de conexión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="1449f-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1449f-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1449f-121">Requirements</span></span>  
  
|<span data-ttu-id="1449f-122">MOF</span><span class="sxs-lookup"><span data-stu-id="1449f-122">MOF</span></span>|<span data-ttu-id="1449f-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1449f-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1449f-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1449f-124">Namespace</span></span>|<span data-ttu-id="1449f-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1449f-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1449f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1449f-126">See also</span></span>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
