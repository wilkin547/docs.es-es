---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: 088754cb15c2e55faa1d43a1da1c79ddcddd69f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280421"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="b71c3-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="b71c3-102">4208 - RetryingSqlCommandDueToSqlError</span></span>

## <a name="properties"></a><span data-ttu-id="b71c3-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b71c3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b71c3-104">ID</span><span class="sxs-lookup"><span data-stu-id="b71c3-104">ID</span></span>|<span data-ttu-id="b71c3-105">4208</span><span class="sxs-lookup"><span data-stu-id="b71c3-105">4208</span></span>|  
|<span data-ttu-id="b71c3-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b71c3-106">Keywords</span></span>|<span data-ttu-id="b71c3-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="b71c3-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="b71c3-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b71c3-108">Level</span></span>|<span data-ttu-id="b71c3-109">Información</span><span class="sxs-lookup"><span data-stu-id="b71c3-109">Information</span></span>|  
|<span data-ttu-id="b71c3-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b71c3-110">Channel</span></span>|<span data-ttu-id="b71c3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b71c3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b71c3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b71c3-112">Description</span></span>  

 <span data-ttu-id="b71c3-113">Indica que el proveedor de SQL está reintentando un comando SQL debido a un error de SQL.</span><span class="sxs-lookup"><span data-stu-id="b71c3-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b71c3-114">Message</span><span class="sxs-lookup"><span data-stu-id="b71c3-114">Message</span></span>  

 <span data-ttu-id="b71c3-115">Reintentando un comando SQL debido al número de error de SQL %1.</span><span class="sxs-lookup"><span data-stu-id="b71c3-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b71c3-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="b71c3-116">Details</span></span>  
  
|<span data-ttu-id="b71c3-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b71c3-117">Data Item Name</span></span>|<span data-ttu-id="b71c3-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b71c3-118">Data Item Type</span></span>|<span data-ttu-id="b71c3-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b71c3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b71c3-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="b71c3-120">ErrorNumber</span></span>|<span data-ttu-id="b71c3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b71c3-121">xs:string</span></span>|<span data-ttu-id="b71c3-122">Número del error de SQL.</span><span class="sxs-lookup"><span data-stu-id="b71c3-122">The SQL error number.</span></span>|  
|<span data-ttu-id="b71c3-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b71c3-123">AppDomain</span></span>|<span data-ttu-id="b71c3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b71c3-124">xs:string</span></span>|<span data-ttu-id="b71c3-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b71c3-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
