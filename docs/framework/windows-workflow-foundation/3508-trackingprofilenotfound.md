---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 23262427c3da730eaf930a8b483c7c4d4ec3a3a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289846"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="59ae2-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="59ae2-102">3508 - TrackingProfileNotFound</span></span>

## <a name="properties"></a><span data-ttu-id="59ae2-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="59ae2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59ae2-104">ID</span><span class="sxs-lookup"><span data-stu-id="59ae2-104">ID</span></span>|<span data-ttu-id="59ae2-105">3508</span><span class="sxs-lookup"><span data-stu-id="59ae2-105">3508</span></span>|  
|<span data-ttu-id="59ae2-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="59ae2-106">Keywords</span></span>|<span data-ttu-id="59ae2-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="59ae2-107">WFServices</span></span>|  
|<span data-ttu-id="59ae2-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="59ae2-108">Level</span></span>|<span data-ttu-id="59ae2-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="59ae2-109">Verbose</span></span>|  
|<span data-ttu-id="59ae2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="59ae2-110">Channel</span></span>|<span data-ttu-id="59ae2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="59ae2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="59ae2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="59ae2-112">Description</span></span>  

 <span data-ttu-id="59ae2-113">Indica que no se encontró un TrackingProfile en el archivo de configuración o que ActivityDefinitionId no coincide con el perfil.</span><span class="sxs-lookup"><span data-stu-id="59ae2-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="59ae2-114">Message</span><span class="sxs-lookup"><span data-stu-id="59ae2-114">Message</span></span>  

 <span data-ttu-id="59ae2-115">No se encontró TrackingProfile '%1' para ActivityDefinitionId '%2'.</span><span class="sxs-lookup"><span data-stu-id="59ae2-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="59ae2-116">No se encontró TrackingProfile en el archivo de configuración o no coincide el ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="59ae2-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="59ae2-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="59ae2-117">Details</span></span>  
  
|<span data-ttu-id="59ae2-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="59ae2-118">Data Item Name</span></span>|<span data-ttu-id="59ae2-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="59ae2-119">Data Item Type</span></span>|<span data-ttu-id="59ae2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="59ae2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="59ae2-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="59ae2-121">TrackingProfile</span></span>|<span data-ttu-id="59ae2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="59ae2-122">xs:string</span></span>|<span data-ttu-id="59ae2-123">El nombre del perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="59ae2-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="59ae2-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="59ae2-124">ActivityDefinitionId</span></span>|<span data-ttu-id="59ae2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="59ae2-125">xs:string</span></span>|<span data-ttu-id="59ae2-126">Identificador de definición de actividad.</span><span class="sxs-lookup"><span data-stu-id="59ae2-126">The activity definition id.</span></span>|  
|<span data-ttu-id="59ae2-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="59ae2-127">AppDomain</span></span>|<span data-ttu-id="59ae2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="59ae2-128">xs:string</span></span>|<span data-ttu-id="59ae2-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="59ae2-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
