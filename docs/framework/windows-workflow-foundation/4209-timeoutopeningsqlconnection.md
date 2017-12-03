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
ms.openlocfilehash: 86d971a2e5f1257281c453e7eb0c2dc1755098d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="af3f7-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="af3f7-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="af3f7-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="af3f7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af3f7-104">Id.</span><span class="sxs-lookup"><span data-stu-id="af3f7-104">ID</span></span>|<span data-ttu-id="af3f7-105">4209</span><span class="sxs-lookup"><span data-stu-id="af3f7-105">4209</span></span>|  
|<span data-ttu-id="af3f7-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="af3f7-106">Keywords</span></span>|<span data-ttu-id="af3f7-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="af3f7-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="af3f7-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="af3f7-108">Level</span></span>|<span data-ttu-id="af3f7-109">Error</span><span class="sxs-lookup"><span data-stu-id="af3f7-109">Error</span></span>|  
|<span data-ttu-id="af3f7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="af3f7-110">Channel</span></span>|<span data-ttu-id="af3f7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="af3f7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="af3f7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="af3f7-112">Description</span></span>  
 <span data-ttu-id="af3f7-113">Indica que se ha alcanzado el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="af3f7-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="af3f7-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="af3f7-114">Message</span></span>  
 <span data-ttu-id="af3f7-115">Se agotó el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="af3f7-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="af3f7-116">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="af3f7-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="af3f7-117">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="af3f7-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="af3f7-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="af3f7-118">Details</span></span>  
  
|<span data-ttu-id="af3f7-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="af3f7-119">Data Item Name</span></span>|<span data-ttu-id="af3f7-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="af3f7-120">Data Item Type</span></span>|<span data-ttu-id="af3f7-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="af3f7-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="af3f7-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="af3f7-122">Timeout</span></span>|<span data-ttu-id="af3f7-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="af3f7-123">xs:string</span></span>|<span data-ttu-id="af3f7-124">Valor de tiempo de espera para abrir la conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="af3f7-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="af3f7-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="af3f7-125">AppDomain</span></span>|<span data-ttu-id="af3f7-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="af3f7-126">xs:string</span></span>|<span data-ttu-id="af3f7-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="af3f7-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
