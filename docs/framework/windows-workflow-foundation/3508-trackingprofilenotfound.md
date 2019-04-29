---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755576"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="59ca7-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="59ca7-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="59ca7-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="59ca7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59ca7-104">ID</span><span class="sxs-lookup"><span data-stu-id="59ca7-104">ID</span></span>|<span data-ttu-id="59ca7-105">3508</span><span class="sxs-lookup"><span data-stu-id="59ca7-105">3508</span></span>|  
|<span data-ttu-id="59ca7-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="59ca7-106">Keywords</span></span>|<span data-ttu-id="59ca7-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="59ca7-107">WFServices</span></span>|  
|<span data-ttu-id="59ca7-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="59ca7-108">Level</span></span>|<span data-ttu-id="59ca7-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="59ca7-109">Verbose</span></span>|  
|<span data-ttu-id="59ca7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="59ca7-110">Channel</span></span>|<span data-ttu-id="59ca7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="59ca7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="59ca7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="59ca7-112">Description</span></span>  
 <span data-ttu-id="59ca7-113">Indica que no se encontró un TrackingProfile en el archivo de configuración o que ActivityDefinitionId no coincide con el perfil.</span><span class="sxs-lookup"><span data-stu-id="59ca7-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="59ca7-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="59ca7-114">Message</span></span>  
 <span data-ttu-id="59ca7-115">No se encontró TrackingProfile '%1' para ActivityDefinitionId '%2'.</span><span class="sxs-lookup"><span data-stu-id="59ca7-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="59ca7-116">No se encontró TrackingProfile en el archivo de configuración o no coincide el ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="59ca7-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="59ca7-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="59ca7-117">Details</span></span>  
  
|<span data-ttu-id="59ca7-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="59ca7-118">Data Item Name</span></span>|<span data-ttu-id="59ca7-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="59ca7-119">Data Item Type</span></span>|<span data-ttu-id="59ca7-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="59ca7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="59ca7-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="59ca7-121">TrackingProfile</span></span>|<span data-ttu-id="59ca7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="59ca7-122">xs:string</span></span>|<span data-ttu-id="59ca7-123">El nombre del perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="59ca7-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="59ca7-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="59ca7-124">ActivityDefinitionId</span></span>|<span data-ttu-id="59ca7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="59ca7-125">xs:string</span></span>|<span data-ttu-id="59ca7-126">Identificador de definición de actividad.</span><span class="sxs-lookup"><span data-stu-id="59ca7-126">The activity definition id.</span></span>|  
|<span data-ttu-id="59ca7-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="59ca7-127">AppDomain</span></span>|<span data-ttu-id="59ca7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="59ca7-128">xs:string</span></span>|<span data-ttu-id="59ca7-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="59ca7-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
