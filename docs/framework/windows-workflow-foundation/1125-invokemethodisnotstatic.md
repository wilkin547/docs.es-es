---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 0405b4e1207db5c056fbd478b98c408258daf0c3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294214"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="0e1b2-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="0e1b2-102">1125 - InvokeMethodIsNotStatic</span></span>

## <a name="properties"></a><span data-ttu-id="0e1b2-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0e1b2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e1b2-104">ID</span><span class="sxs-lookup"><span data-stu-id="0e1b2-104">ID</span></span>|<span data-ttu-id="0e1b2-105">1125</span><span class="sxs-lookup"><span data-stu-id="0e1b2-105">1125</span></span>|  
|<span data-ttu-id="0e1b2-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0e1b2-106">Keywords</span></span>|<span data-ttu-id="0e1b2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0e1b2-107">WFRuntime</span></span>|  
|<span data-ttu-id="0e1b2-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0e1b2-108">Level</span></span>|<span data-ttu-id="0e1b2-109">Información</span><span class="sxs-lookup"><span data-stu-id="0e1b2-109">Information</span></span>|  
|<span data-ttu-id="0e1b2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0e1b2-110">Channel</span></span>|<span data-ttu-id="0e1b2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0e1b2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0e1b2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e1b2-112">Description</span></span>  

 <span data-ttu-id="0e1b2-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que el método que se va a invocar no es estático.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0e1b2-114">Message</span><span class="sxs-lookup"><span data-stu-id="0e1b2-114">Message</span></span>  

 <span data-ttu-id="0e1b2-115">InvokeMethod '%1': el método no es estático.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0e1b2-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="0e1b2-116">Details</span></span>  
  
|<span data-ttu-id="0e1b2-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0e1b2-117">Data Item Name</span></span>|<span data-ttu-id="0e1b2-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0e1b2-118">Data Item Type</span></span>|<span data-ttu-id="0e1b2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e1b2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0e1b2-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="0e1b2-120">InvokeMethod</span></span>|<span data-ttu-id="0e1b2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e1b2-121">xs:string</span></span>|<span data-ttu-id="0e1b2-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="0e1b2-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0e1b2-123">AppDomain</span></span>|<span data-ttu-id="0e1b2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0e1b2-124">xs:string</span></span>|<span data-ttu-id="0e1b2-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
