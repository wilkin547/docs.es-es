---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 0d6326889077e36ad49aa6267ae7285849c6818d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275871"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="3b354-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="3b354-102">4201 - EndSqlCommandExecute</span></span>

## <a name="properties"></a><span data-ttu-id="3b354-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3b354-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b354-104">ID</span><span class="sxs-lookup"><span data-stu-id="3b354-104">ID</span></span>|<span data-ttu-id="3b354-105">4201</span><span class="sxs-lookup"><span data-stu-id="3b354-105">4201</span></span>|  
|<span data-ttu-id="3b354-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3b354-106">Keywords</span></span>|<span data-ttu-id="3b354-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3b354-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3b354-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3b354-108">Level</span></span>|<span data-ttu-id="3b354-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="3b354-109">Verbose</span></span>|  
|<span data-ttu-id="3b354-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3b354-110">Channel</span></span>|<span data-ttu-id="3b354-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3b354-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3b354-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b354-112">Description</span></span>  

 <span data-ttu-id="3b354-113">Indica que un comando SQL ha terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="3b354-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3b354-114">Message</span><span class="sxs-lookup"><span data-stu-id="3b354-114">Message</span></span>  

 <span data-ttu-id="3b354-115">Ejecución de comando SQL final: %1</span><span class="sxs-lookup"><span data-stu-id="3b354-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="3b354-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="3b354-116">Details</span></span>  
  
|<span data-ttu-id="3b354-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3b354-117">Data Item Name</span></span>|<span data-ttu-id="3b354-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3b354-118">Data Item Type</span></span>|<span data-ttu-id="3b354-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b354-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3b354-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="3b354-120">SqlCommand</span></span>|<span data-ttu-id="3b354-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b354-121">xs:string</span></span>|<span data-ttu-id="3b354-122">El comando SQL que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="3b354-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="3b354-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3b354-123">AppDomain</span></span>|<span data-ttu-id="3b354-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b354-124">xs:string</span></span>|<span data-ttu-id="3b354-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3b354-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
