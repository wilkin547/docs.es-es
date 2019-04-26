---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 64701d4c38c042e8273129be19f9caeb2c442abf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924220"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="f739a-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="f739a-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="f739a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f739a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f739a-104">ID</span><span class="sxs-lookup"><span data-stu-id="f739a-104">ID</span></span>|<span data-ttu-id="f739a-105">1132</span><span class="sxs-lookup"><span data-stu-id="f739a-105">1132</span></span>|  
|<span data-ttu-id="f739a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f739a-106">Keywords</span></span>|<span data-ttu-id="f739a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f739a-107">WFRuntime</span></span>|  
|<span data-ttu-id="f739a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f739a-108">Level</span></span>|<span data-ttu-id="f739a-109">Información</span><span class="sxs-lookup"><span data-stu-id="f739a-109">Information</span></span>|  
|<span data-ttu-id="f739a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f739a-110">Channel</span></span>|<span data-ttu-id="f739a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f739a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f739a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f739a-112">Description</span></span>  
 <span data-ttu-id="f739a-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="f739a-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f739a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f739a-114">Message</span></span>  
 <span data-ttu-id="f739a-115">InvokeMethod '%1': el método no usa un patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="f739a-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f739a-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="f739a-116">Details</span></span>  
  
|<span data-ttu-id="f739a-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f739a-117">Data Item Name</span></span>|<span data-ttu-id="f739a-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f739a-118">Data Item Type</span></span>|<span data-ttu-id="f739a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f739a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f739a-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="f739a-120">InvokeMethod</span></span>|<span data-ttu-id="f739a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f739a-121">xs:string</span></span>|<span data-ttu-id="f739a-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="f739a-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="f739a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f739a-123">AppDomain</span></span>|<span data-ttu-id="f739a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f739a-124">xs:string</span></span>|<span data-ttu-id="f739a-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f739a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
