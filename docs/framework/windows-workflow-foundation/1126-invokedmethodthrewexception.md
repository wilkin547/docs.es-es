---
title: 1126 - InvokedMethodThrewException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b11c2f167ce7afce992cddb2f32f840212d4ac8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="f2336-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="f2336-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="f2336-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f2336-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2336-104">Id.</span><span class="sxs-lookup"><span data-stu-id="f2336-104">ID</span></span>|<span data-ttu-id="f2336-105">1126</span><span class="sxs-lookup"><span data-stu-id="f2336-105">1126</span></span>|  
|<span data-ttu-id="f2336-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f2336-106">Keywords</span></span>|<span data-ttu-id="f2336-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f2336-107">WFRuntime</span></span>|  
|<span data-ttu-id="f2336-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f2336-108">Level</span></span>|<span data-ttu-id="f2336-109">Información</span><span class="sxs-lookup"><span data-stu-id="f2336-109">Information</span></span>|  
|<span data-ttu-id="f2336-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f2336-110">Channel</span></span>|<span data-ttu-id="f2336-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f2336-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f2336-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2336-112">Description</span></span>  
 <span data-ttu-id="f2336-113">Indica que se produjo una excepción en el método invocado por la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="f2336-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f2336-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f2336-114">Message</span></span>  
 <span data-ttu-id="f2336-115">Se produjo una excepción en el método invocado por la actividad '%1'</span><span class="sxs-lookup"><span data-stu-id="f2336-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="f2336-116">%2</span><span class="sxs-lookup"><span data-stu-id="f2336-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="f2336-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="f2336-117">Details</span></span>  
  
|<span data-ttu-id="f2336-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f2336-118">Data Item Name</span></span>|<span data-ttu-id="f2336-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f2336-119">Data Item Type</span></span>|<span data-ttu-id="f2336-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2336-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f2336-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="f2336-121">InvokeMethod</span></span>|<span data-ttu-id="f2336-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2336-122">xs:string</span></span>|<span data-ttu-id="f2336-123">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="f2336-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="f2336-124">Excepción</span><span class="sxs-lookup"><span data-stu-id="f2336-124">Exception</span></span>|<span data-ttu-id="f2336-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2336-125">xs:string</span></span>|<span data-ttu-id="f2336-126">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="f2336-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="f2336-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f2336-127">AppDomain</span></span>|<span data-ttu-id="f2336-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2336-128">xs:string</span></span>|<span data-ttu-id="f2336-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f2336-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
