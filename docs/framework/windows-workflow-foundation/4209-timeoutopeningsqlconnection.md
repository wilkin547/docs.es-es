---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513170"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="6d8b9-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="6d8b9-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="6d8b9-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6d8b9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d8b9-104">Id.</span><span class="sxs-lookup"><span data-stu-id="6d8b9-104">ID</span></span>|<span data-ttu-id="6d8b9-105">4209</span><span class="sxs-lookup"><span data-stu-id="6d8b9-105">4209</span></span>|  
|<span data-ttu-id="6d8b9-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6d8b9-106">Keywords</span></span>|<span data-ttu-id="6d8b9-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="6d8b9-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="6d8b9-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6d8b9-108">Level</span></span>|<span data-ttu-id="6d8b9-109">Error</span><span class="sxs-lookup"><span data-stu-id="6d8b9-109">Error</span></span>|  
|<span data-ttu-id="6d8b9-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6d8b9-110">Channel</span></span>|<span data-ttu-id="6d8b9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6d8b9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6d8b9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d8b9-112">Description</span></span>  
 <span data-ttu-id="6d8b9-113">Indica que se ha alcanzado el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="6d8b9-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6d8b9-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="6d8b9-114">Message</span></span>  
 <span data-ttu-id="6d8b9-115">Se agotó el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="6d8b9-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="6d8b9-116">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="6d8b9-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="6d8b9-117">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="6d8b9-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6d8b9-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="6d8b9-118">Details</span></span>  
  
|<span data-ttu-id="6d8b9-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6d8b9-119">Data Item Name</span></span>|<span data-ttu-id="6d8b9-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6d8b9-120">Data Item Type</span></span>|<span data-ttu-id="6d8b9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d8b9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6d8b9-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="6d8b9-122">Timeout</span></span>|<span data-ttu-id="6d8b9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d8b9-123">xs:string</span></span>|<span data-ttu-id="6d8b9-124">Valor de tiempo de espera para abrir la conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="6d8b9-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="6d8b9-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6d8b9-125">AppDomain</span></span>|<span data-ttu-id="6d8b9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="6d8b9-126">xs:string</span></span>|<span data-ttu-id="6d8b9-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6d8b9-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
