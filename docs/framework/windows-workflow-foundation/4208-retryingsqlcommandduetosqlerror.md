---
description: 'Más información acerca de: 4208-RetryingSqlCommandDueToSqlError'
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 11ea2260f6a2ceffc1ffdbfce2cb3e3ce784076d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755309"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="fe3a0-103">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="fe3a0-103">4208 - RetryingSqlCommandDueToSqlError</span></span>

## <a name="properties"></a><span data-ttu-id="fe3a0-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fe3a0-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe3a0-105">Id.</span><span class="sxs-lookup"><span data-stu-id="fe3a0-105">ID</span></span>|<span data-ttu-id="fe3a0-106">4208</span><span class="sxs-lookup"><span data-stu-id="fe3a0-106">4208</span></span>|  
|<span data-ttu-id="fe3a0-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fe3a0-107">Keywords</span></span>|<span data-ttu-id="fe3a0-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="fe3a0-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="fe3a0-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="fe3a0-109">Level</span></span>|<span data-ttu-id="fe3a0-110">Información</span><span class="sxs-lookup"><span data-stu-id="fe3a0-110">Information</span></span>|  
|<span data-ttu-id="fe3a0-111">Canal</span><span class="sxs-lookup"><span data-stu-id="fe3a0-111">Channel</span></span>|<span data-ttu-id="fe3a0-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fe3a0-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe3a0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe3a0-113">Description</span></span>  

 <span data-ttu-id="fe3a0-114">Indica que el proveedor de SQL está reintentando un comando SQL debido a un error de SQL.</span><span class="sxs-lookup"><span data-stu-id="fe3a0-114">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fe3a0-115">Message</span><span class="sxs-lookup"><span data-stu-id="fe3a0-115">Message</span></span>  

 <span data-ttu-id="fe3a0-116">Reintentando un comando SQL debido al número de error de SQL %1.</span><span class="sxs-lookup"><span data-stu-id="fe3a0-116">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fe3a0-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="fe3a0-117">Details</span></span>  
  
|<span data-ttu-id="fe3a0-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fe3a0-118">Data Item Name</span></span>|<span data-ttu-id="fe3a0-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fe3a0-119">Data Item Type</span></span>|<span data-ttu-id="fe3a0-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe3a0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fe3a0-121">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="fe3a0-121">ErrorNumber</span></span>|<span data-ttu-id="fe3a0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe3a0-122">xs:string</span></span>|<span data-ttu-id="fe3a0-123">Número del error de SQL.</span><span class="sxs-lookup"><span data-stu-id="fe3a0-123">The SQL error number.</span></span>|  
|<span data-ttu-id="fe3a0-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fe3a0-124">AppDomain</span></span>|<span data-ttu-id="fe3a0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe3a0-125">xs:string</span></span>|<span data-ttu-id="fe3a0-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fe3a0-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
