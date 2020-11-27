---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: d3f27c6ed28efe9d099dcedfc676b839ae9b1dee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275845"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="e8a03-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="e8a03-102">4202 - StartSqlCommandExecute</span></span>

## <a name="properties"></a><span data-ttu-id="e8a03-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e8a03-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8a03-104">ID</span><span class="sxs-lookup"><span data-stu-id="e8a03-104">ID</span></span>|<span data-ttu-id="e8a03-105">4202</span><span class="sxs-lookup"><span data-stu-id="e8a03-105">4202</span></span>|  
|<span data-ttu-id="e8a03-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e8a03-106">Keywords</span></span>|<span data-ttu-id="e8a03-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="e8a03-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="e8a03-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e8a03-108">Level</span></span>|<span data-ttu-id="e8a03-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="e8a03-109">Verbose</span></span>|  
|<span data-ttu-id="e8a03-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e8a03-110">Channel</span></span>|<span data-ttu-id="e8a03-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e8a03-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e8a03-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8a03-112">Description</span></span>  

 <span data-ttu-id="e8a03-113">Indica que se está ejecutando un comando SQL.</span><span class="sxs-lookup"><span data-stu-id="e8a03-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e8a03-114">Message</span><span class="sxs-lookup"><span data-stu-id="e8a03-114">Message</span></span>  

 <span data-ttu-id="e8a03-115">Ejecución de comando SQL inicial: %1</span><span class="sxs-lookup"><span data-stu-id="e8a03-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="e8a03-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="e8a03-116">Details</span></span>  
  
|<span data-ttu-id="e8a03-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e8a03-117">Data Item Name</span></span>|<span data-ttu-id="e8a03-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e8a03-118">Data Item Type</span></span>|<span data-ttu-id="e8a03-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8a03-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e8a03-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="e8a03-120">SqlCommand</span></span>|<span data-ttu-id="e8a03-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8a03-121">xs:string</span></span>|<span data-ttu-id="e8a03-122">El comando SQL que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="e8a03-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="e8a03-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e8a03-123">AppDomain</span></span>|<span data-ttu-id="e8a03-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8a03-124">xs:string</span></span>|<span data-ttu-id="e8a03-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e8a03-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
