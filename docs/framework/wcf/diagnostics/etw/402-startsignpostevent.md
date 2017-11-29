---
title: 402 - StartSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c0cd786f78336be50ad2ef5447f74b92b2abbdc7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="402---startsignpostevent"></a><span data-ttu-id="efe54-102">402 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="efe54-102">402 - StartSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="efe54-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="efe54-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efe54-104">Id.</span><span class="sxs-lookup"><span data-stu-id="efe54-104">ID</span></span>|<span data-ttu-id="efe54-105">402</span><span class="sxs-lookup"><span data-stu-id="efe54-105">402</span></span>|  
|<span data-ttu-id="efe54-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="efe54-106">Keywords</span></span>|<span data-ttu-id="efe54-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="efe54-107">Troubleshooting</span></span>|  
|<span data-ttu-id="efe54-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="efe54-108">Level</span></span>|<span data-ttu-id="efe54-109">Información</span><span class="sxs-lookup"><span data-stu-id="efe54-109">Information</span></span>|  
|<span data-ttu-id="efe54-110">Canal</span><span class="sxs-lookup"><span data-stu-id="efe54-110">Channel</span></span>|<span data-ttu-id="efe54-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="efe54-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="efe54-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="efe54-112">Description</span></span>  
 <span data-ttu-id="efe54-113">Este evento marca el inicio de una actividad de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="efe54-113">This event marks the beginning of an end-to-end activity.</span></span> <span data-ttu-id="efe54-114">Contiene el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="efe54-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="efe54-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="efe54-115">Message</span></span>  
 <span data-ttu-id="efe54-116">Límite de la actividad.</span><span class="sxs-lookup"><span data-stu-id="efe54-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="efe54-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="efe54-117">Details</span></span>  
  
|<span data-ttu-id="efe54-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="efe54-118">Data Item Name</span></span>|<span data-ttu-id="efe54-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="efe54-119">Data Item Type</span></span>|<span data-ttu-id="efe54-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="efe54-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="efe54-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="efe54-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="efe54-122">El nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="efe54-122">The name of the activity.</span></span>|  
|<span data-ttu-id="efe54-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="efe54-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="efe54-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="efe54-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
