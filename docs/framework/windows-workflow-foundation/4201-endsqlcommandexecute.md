---
description: 'Más información acerca de: 4201-EndSqlCommandExecute'
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: e0b98e8da5a0a284bfa55e97f5dde25a2ce42b42
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755374"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="0cfe4-103">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="0cfe4-103">4201 - EndSqlCommandExecute</span></span>

## <a name="properties"></a><span data-ttu-id="0cfe4-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0cfe4-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0cfe4-105">Id.</span><span class="sxs-lookup"><span data-stu-id="0cfe4-105">ID</span></span>|<span data-ttu-id="0cfe4-106">4201</span><span class="sxs-lookup"><span data-stu-id="0cfe4-106">4201</span></span>|  
|<span data-ttu-id="0cfe4-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0cfe4-107">Keywords</span></span>|<span data-ttu-id="0cfe4-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="0cfe4-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="0cfe4-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="0cfe4-109">Level</span></span>|<span data-ttu-id="0cfe4-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="0cfe4-110">Verbose</span></span>|  
|<span data-ttu-id="0cfe4-111">Canal</span><span class="sxs-lookup"><span data-stu-id="0cfe4-111">Channel</span></span>|<span data-ttu-id="0cfe4-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0cfe4-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0cfe4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cfe4-113">Description</span></span>  

 <span data-ttu-id="0cfe4-114">Indica que un comando SQL ha terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="0cfe4-114">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0cfe4-115">Message</span><span class="sxs-lookup"><span data-stu-id="0cfe4-115">Message</span></span>  

 <span data-ttu-id="0cfe4-116">Ejecución de comando SQL final: %1</span><span class="sxs-lookup"><span data-stu-id="0cfe4-116">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="0cfe4-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="0cfe4-117">Details</span></span>  
  
|<span data-ttu-id="0cfe4-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0cfe4-118">Data Item Name</span></span>|<span data-ttu-id="0cfe4-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0cfe4-119">Data Item Type</span></span>|<span data-ttu-id="0cfe4-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cfe4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0cfe4-121">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="0cfe4-121">SqlCommand</span></span>|<span data-ttu-id="0cfe4-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0cfe4-122">xs:string</span></span>|<span data-ttu-id="0cfe4-123">El comando SQL que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="0cfe4-123">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="0cfe4-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0cfe4-124">AppDomain</span></span>|<span data-ttu-id="0cfe4-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0cfe4-125">xs:string</span></span>|<span data-ttu-id="0cfe4-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0cfe4-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
