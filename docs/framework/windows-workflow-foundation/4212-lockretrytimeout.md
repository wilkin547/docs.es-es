---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774223"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="7ea17-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="7ea17-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="7ea17-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7ea17-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ea17-104">ID</span><span class="sxs-lookup"><span data-stu-id="7ea17-104">ID</span></span>|<span data-ttu-id="7ea17-105">4212</span><span class="sxs-lookup"><span data-stu-id="7ea17-105">4212</span></span>|  
|<span data-ttu-id="7ea17-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7ea17-106">Keywords</span></span>|<span data-ttu-id="7ea17-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="7ea17-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="7ea17-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="7ea17-108">Level</span></span>|<span data-ttu-id="7ea17-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="7ea17-109">Warning</span></span>|  
|<span data-ttu-id="7ea17-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7ea17-110">Channel</span></span>|<span data-ttu-id="7ea17-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7ea17-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7ea17-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ea17-112">Description</span></span>  
 <span data-ttu-id="7ea17-113">El proveedor de SQL detectó que se agotó el tiempo de espera al intentar adquirir el bloqueo de instancia.</span><span class="sxs-lookup"><span data-stu-id="7ea17-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7ea17-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7ea17-114">Message</span></span>  
 <span data-ttu-id="7ea17-115">Tiempo de espera al intentar adquirir el bloqueo de la instancia.</span><span class="sxs-lookup"><span data-stu-id="7ea17-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="7ea17-116">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="7ea17-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="7ea17-117">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="7ea17-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7ea17-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="7ea17-118">Details</span></span>  
  
|<span data-ttu-id="7ea17-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7ea17-119">Data Item Name</span></span>|<span data-ttu-id="7ea17-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7ea17-120">Data Item Type</span></span>|<span data-ttu-id="7ea17-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ea17-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7ea17-122">Delay</span><span class="sxs-lookup"><span data-stu-id="7ea17-122">Delay</span></span>|<span data-ttu-id="7ea17-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ea17-123">xs:string</span></span>|<span data-ttu-id="7ea17-124">Retraso entre los intentos.</span><span class="sxs-lookup"><span data-stu-id="7ea17-124">The delay between retries.</span></span>|  
|<span data-ttu-id="7ea17-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7ea17-125">AppDomain</span></span>|<span data-ttu-id="7ea17-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ea17-126">xs:string</span></span>|<span data-ttu-id="7ea17-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7ea17-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
