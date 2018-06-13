---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512189"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="f8736-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="f8736-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="f8736-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f8736-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8736-104">Id.</span><span class="sxs-lookup"><span data-stu-id="f8736-104">ID</span></span>|<span data-ttu-id="f8736-105">3508</span><span class="sxs-lookup"><span data-stu-id="f8736-105">3508</span></span>|  
|<span data-ttu-id="f8736-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f8736-106">Keywords</span></span>|<span data-ttu-id="f8736-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f8736-107">WFServices</span></span>|  
|<span data-ttu-id="f8736-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f8736-108">Level</span></span>|<span data-ttu-id="f8736-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="f8736-109">Verbose</span></span>|  
|<span data-ttu-id="f8736-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f8736-110">Channel</span></span>|<span data-ttu-id="f8736-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f8736-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f8736-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8736-112">Description</span></span>  
 <span data-ttu-id="f8736-113">Indica que no se encontró un TrackingProfile en el archivo de configuración o que ActivityDefinitionId no coincide con el perfil.</span><span class="sxs-lookup"><span data-stu-id="f8736-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f8736-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f8736-114">Message</span></span>  
 <span data-ttu-id="f8736-115">No se encontró TrackingProfile '%1' para ActivityDefinitionId '%2'.</span><span class="sxs-lookup"><span data-stu-id="f8736-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="f8736-116">No se encontró TrackingProfile en el archivo de configuración o no coincide el ActivityDefinitionId.</span><span class="sxs-lookup"><span data-stu-id="f8736-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f8736-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="f8736-117">Details</span></span>  
  
|<span data-ttu-id="f8736-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f8736-118">Data Item Name</span></span>|<span data-ttu-id="f8736-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f8736-119">Data Item Type</span></span>|<span data-ttu-id="f8736-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8736-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f8736-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="f8736-121">TrackingProfile</span></span>|<span data-ttu-id="f8736-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8736-122">xs:string</span></span>|<span data-ttu-id="f8736-123">El nombre del perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f8736-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="f8736-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="f8736-124">ActivityDefinitionId</span></span>|<span data-ttu-id="f8736-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8736-125">xs:string</span></span>|<span data-ttu-id="f8736-126">Identificador de definición de actividad.</span><span class="sxs-lookup"><span data-stu-id="f8736-126">The activity definition id.</span></span>|  
|<span data-ttu-id="f8736-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f8736-127">AppDomain</span></span>|<span data-ttu-id="f8736-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f8736-128">xs:string</span></span>|<span data-ttu-id="f8736-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f8736-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
