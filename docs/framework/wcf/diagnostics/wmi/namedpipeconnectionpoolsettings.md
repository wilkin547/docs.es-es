---
description: 'Más información acerca de: NamedPipeConnectionPoolSettings'
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8d724c7a24f62a8d48797125528eb8a194ece660
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803118"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="8df17-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8df17-103">NamedPipeConnectionPoolSettings</span></span>

<span data-ttu-id="8df17-104">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8df17-104">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8df17-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8df17-105">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8df17-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="8df17-106">Methods</span></span>  

 <span data-ttu-id="8df17-107">La clase NamedPipeConnectionPoolSettings no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="8df17-107">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8df17-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8df17-108">Properties</span></span>  

 <span data-ttu-id="8df17-109">La clase NamedPipeConnectionPoolSettings tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="8df17-109">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="8df17-110">NombreDeGrupo</span><span class="sxs-lookup"><span data-stu-id="8df17-110">GroupName</span></span>  

 <span data-ttu-id="8df17-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8df17-111">Data type: string</span></span>  
  
 <span data-ttu-id="8df17-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8df17-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8df17-113">El nombre del grupo de conexiones utilizado por el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="8df17-113">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="8df17-114">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="8df17-114">IdleTimeout</span></span>  

 <span data-ttu-id="8df17-115">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="8df17-115">Data type: datetime</span></span>  
  
 <span data-ttu-id="8df17-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8df17-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8df17-117">El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.</span><span class="sxs-lookup"><span data-stu-id="8df17-117">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="8df17-118">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="8df17-118">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="8df17-119">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="8df17-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="8df17-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="8df17-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8df17-121">El número máximo de conexiones salientes para cada punto de conexión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="8df17-121">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8df17-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8df17-122">Requirements</span></span>  
  
|<span data-ttu-id="8df17-123">MOF</span><span class="sxs-lookup"><span data-stu-id="8df17-123">MOF</span></span>|<span data-ttu-id="8df17-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8df17-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8df17-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="8df17-125">Namespace</span></span>|<span data-ttu-id="8df17-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8df17-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8df17-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8df17-127">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
