---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774275"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="43d77-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="43d77-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="43d77-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="43d77-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43d77-104">ID</span><span class="sxs-lookup"><span data-stu-id="43d77-104">ID</span></span>|<span data-ttu-id="43d77-105">4209</span><span class="sxs-lookup"><span data-stu-id="43d77-105">4209</span></span>|  
|<span data-ttu-id="43d77-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="43d77-106">Keywords</span></span>|<span data-ttu-id="43d77-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="43d77-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="43d77-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="43d77-108">Level</span></span>|<span data-ttu-id="43d77-109">Error</span><span class="sxs-lookup"><span data-stu-id="43d77-109">Error</span></span>|  
|<span data-ttu-id="43d77-110">Canal</span><span class="sxs-lookup"><span data-stu-id="43d77-110">Channel</span></span>|<span data-ttu-id="43d77-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="43d77-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="43d77-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="43d77-112">Description</span></span>  
 <span data-ttu-id="43d77-113">Indica que se ha alcanzado el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="43d77-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="43d77-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="43d77-114">Message</span></span>  
 <span data-ttu-id="43d77-115">Se agotó el tiempo de espera al intentar abrir una conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="43d77-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="43d77-116">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="43d77-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="43d77-117">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="43d77-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="43d77-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="43d77-118">Details</span></span>  
  
|<span data-ttu-id="43d77-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="43d77-119">Data Item Name</span></span>|<span data-ttu-id="43d77-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="43d77-120">Data Item Type</span></span>|<span data-ttu-id="43d77-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="43d77-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="43d77-122">Tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="43d77-122">Timeout</span></span>|<span data-ttu-id="43d77-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="43d77-123">xs:string</span></span>|<span data-ttu-id="43d77-124">Valor de tiempo de espera para abrir la conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="43d77-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="43d77-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="43d77-125">AppDomain</span></span>|<span data-ttu-id="43d77-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="43d77-126">xs:string</span></span>|<span data-ttu-id="43d77-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="43d77-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
