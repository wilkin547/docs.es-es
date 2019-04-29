---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774301"
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="3950a-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="3950a-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="3950a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3950a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3950a-104">ID</span><span class="sxs-lookup"><span data-stu-id="3950a-104">ID</span></span>|<span data-ttu-id="3950a-105">4208</span><span class="sxs-lookup"><span data-stu-id="3950a-105">4208</span></span>|  
|<span data-ttu-id="3950a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3950a-106">Keywords</span></span>|<span data-ttu-id="3950a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3950a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3950a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3950a-108">Level</span></span>|<span data-ttu-id="3950a-109">Información</span><span class="sxs-lookup"><span data-stu-id="3950a-109">Information</span></span>|  
|<span data-ttu-id="3950a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3950a-110">Channel</span></span>|<span data-ttu-id="3950a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3950a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3950a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3950a-112">Description</span></span>  
 <span data-ttu-id="3950a-113">Indica que el proveedor de SQL está reintentando un comando SQL debido a un error de SQL.</span><span class="sxs-lookup"><span data-stu-id="3950a-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3950a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3950a-114">Message</span></span>  
 <span data-ttu-id="3950a-115">Reintentando un comando SQL debido al número de error de SQL %1.</span><span class="sxs-lookup"><span data-stu-id="3950a-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3950a-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="3950a-116">Details</span></span>  
  
|<span data-ttu-id="3950a-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3950a-117">Data Item Name</span></span>|<span data-ttu-id="3950a-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3950a-118">Data Item Type</span></span>|<span data-ttu-id="3950a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3950a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3950a-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="3950a-120">ErrorNumber</span></span>|<span data-ttu-id="3950a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3950a-121">xs:string</span></span>|<span data-ttu-id="3950a-122">Número del error de SQL.</span><span class="sxs-lookup"><span data-stu-id="3950a-122">The SQL error number.</span></span>|  
|<span data-ttu-id="3950a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3950a-123">AppDomain</span></span>|<span data-ttu-id="3950a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3950a-124">xs:string</span></span>|<span data-ttu-id="3950a-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3950a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
