---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7528c967cbd88f00af448d6163c10e807f603bc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="0acaa-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="0acaa-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="0acaa-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0acaa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0acaa-104">Id.</span><span class="sxs-lookup"><span data-stu-id="0acaa-104">ID</span></span>|<span data-ttu-id="0acaa-105">4209</span><span class="sxs-lookup"><span data-stu-id="0acaa-105">4209</span></span>|  
|<span data-ttu-id="0acaa-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0acaa-106">Keywords</span></span>|<span data-ttu-id="0acaa-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="0acaa-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="0acaa-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0acaa-108">Level</span></span>|<span data-ttu-id="0acaa-109">Error</span><span class="sxs-lookup"><span data-stu-id="0acaa-109">Error</span></span>|  
|<span data-ttu-id="0acaa-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0acaa-110">Channel</span></span>|<span data-ttu-id="0acaa-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0acaa-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0acaa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0acaa-112">Description</span></span>  
 <span data-ttu-id="0acaa-113">Indica que se ha alcanzado el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="0acaa-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0acaa-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0acaa-114">Message</span></span>  
 <span data-ttu-id="0acaa-115">Se agotó el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="0acaa-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="0acaa-116">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="0acaa-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="0acaa-117">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="0acaa-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0acaa-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="0acaa-118">Details</span></span>  
  
|<span data-ttu-id="0acaa-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0acaa-119">Data Item Name</span></span>|<span data-ttu-id="0acaa-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0acaa-120">Data Item Type</span></span>|<span data-ttu-id="0acaa-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="0acaa-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0acaa-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="0acaa-122">Timeout</span></span>|<span data-ttu-id="0acaa-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="0acaa-123">xs:string</span></span>|<span data-ttu-id="0acaa-124">Valor de tiempo de espera para abrir la conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="0acaa-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="0acaa-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0acaa-125">AppDomain</span></span>|<span data-ttu-id="0acaa-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="0acaa-126">xs:string</span></span>|<span data-ttu-id="0acaa-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0acaa-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
