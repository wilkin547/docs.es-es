---
title: 4201 - EndSqlCommandExecute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 57c413ddae884f50e8f65eac146ccf5b2fc84b8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="012d8-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="012d8-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="012d8-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="012d8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="012d8-104">Id.</span><span class="sxs-lookup"><span data-stu-id="012d8-104">ID</span></span>|<span data-ttu-id="012d8-105">4201</span><span class="sxs-lookup"><span data-stu-id="012d8-105">4201</span></span>|  
|<span data-ttu-id="012d8-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="012d8-106">Keywords</span></span>|<span data-ttu-id="012d8-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="012d8-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="012d8-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="012d8-108">Level</span></span>|<span data-ttu-id="012d8-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="012d8-109">Verbose</span></span>|  
|<span data-ttu-id="012d8-110">Canal</span><span class="sxs-lookup"><span data-stu-id="012d8-110">Channel</span></span>|<span data-ttu-id="012d8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="012d8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="012d8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="012d8-112">Description</span></span>  
 <span data-ttu-id="012d8-113">Indica que un comando SQL ha terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="012d8-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="012d8-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="012d8-114">Message</span></span>  
 <span data-ttu-id="012d8-115">Ejecución de comando SQL final: %1</span><span class="sxs-lookup"><span data-stu-id="012d8-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="012d8-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="012d8-116">Details</span></span>  
  
|<span data-ttu-id="012d8-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="012d8-117">Data Item Name</span></span>|<span data-ttu-id="012d8-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="012d8-118">Data Item Type</span></span>|<span data-ttu-id="012d8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="012d8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="012d8-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="012d8-120">SqlCommand</span></span>|<span data-ttu-id="012d8-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="012d8-121">xs:string</span></span>|<span data-ttu-id="012d8-122">El comando SQL que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="012d8-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="012d8-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="012d8-123">AppDomain</span></span>|<span data-ttu-id="012d8-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="012d8-124">xs:string</span></span>|<span data-ttu-id="012d8-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="012d8-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
