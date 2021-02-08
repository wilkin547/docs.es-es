---
description: 'Más información acerca de: 4209-TimeoutOpeningSqlConnection'
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: 9c7540e328530fdc01b9f065dfb75b92c467bd43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787999"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="5d18d-103">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="5d18d-103">4209 - TimeoutOpeningSqlConnection</span></span>

## <a name="properties"></a><span data-ttu-id="5d18d-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5d18d-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d18d-105">Id.</span><span class="sxs-lookup"><span data-stu-id="5d18d-105">ID</span></span>|<span data-ttu-id="5d18d-106">4209</span><span class="sxs-lookup"><span data-stu-id="5d18d-106">4209</span></span>|  
|<span data-ttu-id="5d18d-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d18d-107">Keywords</span></span>|<span data-ttu-id="5d18d-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5d18d-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="5d18d-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="5d18d-109">Level</span></span>|<span data-ttu-id="5d18d-110">Error</span><span class="sxs-lookup"><span data-stu-id="5d18d-110">Error</span></span>|  
|<span data-ttu-id="5d18d-111">Canal</span><span class="sxs-lookup"><span data-stu-id="5d18d-111">Channel</span></span>|<span data-ttu-id="5d18d-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5d18d-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d18d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d18d-113">Description</span></span>  

 <span data-ttu-id="5d18d-114">Indica que se ha alcanzado el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="5d18d-114">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d18d-115">Message</span><span class="sxs-lookup"><span data-stu-id="5d18d-115">Message</span></span>  

 <span data-ttu-id="5d18d-116">Se agotó el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="5d18d-116">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="5d18d-117">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="5d18d-117">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="5d18d-118">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="5d18d-118">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d18d-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d18d-119">Details</span></span>  
  
|<span data-ttu-id="5d18d-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5d18d-120">Data Item Name</span></span>|<span data-ttu-id="5d18d-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5d18d-121">Data Item Type</span></span>|<span data-ttu-id="5d18d-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d18d-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d18d-123">Tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="5d18d-123">Timeout</span></span>|<span data-ttu-id="5d18d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d18d-124">xs:string</span></span>|<span data-ttu-id="5d18d-125">Valor de tiempo de espera para abrir la conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="5d18d-125">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="5d18d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d18d-126">AppDomain</span></span>|<span data-ttu-id="5d18d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d18d-127">xs:string</span></span>|<span data-ttu-id="5d18d-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5d18d-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
