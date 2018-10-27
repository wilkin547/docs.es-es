---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 77d8403947d341ea2efcef98bbf166f94f75f31f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188734"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="1de8c-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1de8c-102">NamedPipeConnectionPoolSettings</span></span>
<span data-ttu-id="1de8c-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="1de8c-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de8c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1de8c-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1de8c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1de8c-105">Methods</span></span>  
 <span data-ttu-id="1de8c-106">La clase NamedPipeConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1de8c-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1de8c-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1de8c-107">Properties</span></span>  
 <span data-ttu-id="1de8c-108">La clase NamedPipeConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1de8c-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="1de8c-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="1de8c-109">GroupName</span></span>  
 <span data-ttu-id="1de8c-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1de8c-110">Data type: string</span></span>  
  
 <span data-ttu-id="1de8c-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1de8c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1de8c-112">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="1de8c-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="1de8c-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="1de8c-113">IdleTimeout</span></span>  
 <span data-ttu-id="1de8c-114">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="1de8c-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="1de8c-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1de8c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1de8c-116">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="1de8c-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="1de8c-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="1de8c-117">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="1de8c-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="1de8c-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="1de8c-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1de8c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1de8c-120">El número máximo de conexiones salientes para cada extremo en el cliente.</span><span class="sxs-lookup"><span data-stu-id="1de8c-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de8c-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1de8c-121">Requirements</span></span>  
  
|<span data-ttu-id="1de8c-122">MOF</span><span class="sxs-lookup"><span data-stu-id="1de8c-122">MOF</span></span>|<span data-ttu-id="1de8c-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1de8c-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1de8c-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1de8c-124">Namespace</span></span>|<span data-ttu-id="1de8c-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1de8c-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1de8c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1de8c-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
