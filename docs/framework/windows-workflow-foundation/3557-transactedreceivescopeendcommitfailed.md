---
description: 'Más información acerca de: 3557-TransactedReceiveScopeEndCommitFailed'
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 7865ae27e7ce5b3f13b3567f3f8aeebd6edf3fd4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777988"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="875e8-103">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="875e8-103">3557 - TransactedReceiveScopeEndCommitFailed</span></span>

## <a name="properties"></a><span data-ttu-id="875e8-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="875e8-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="875e8-105">Id.</span><span class="sxs-lookup"><span data-stu-id="875e8-105">ID</span></span>|<span data-ttu-id="875e8-106">3557</span><span class="sxs-lookup"><span data-stu-id="875e8-106">3557</span></span>|  
|<span data-ttu-id="875e8-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="875e8-107">Keywords</span></span>|<span data-ttu-id="875e8-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="875e8-108">WFServices</span></span>|  
|<span data-ttu-id="875e8-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="875e8-109">Level</span></span>|<span data-ttu-id="875e8-110">Información</span><span class="sxs-lookup"><span data-stu-id="875e8-110">Information</span></span>|  
|<span data-ttu-id="875e8-111">Canal</span><span class="sxs-lookup"><span data-stu-id="875e8-111">Channel</span></span>|<span data-ttu-id="875e8-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="875e8-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="875e8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="875e8-113">Description</span></span>  

 <span data-ttu-id="875e8-114">Indica que la llamada a EndCommit en un CommittableTransaction produjo una TransactionException.</span><span class="sxs-lookup"><span data-stu-id="875e8-114">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="875e8-115">Message</span><span class="sxs-lookup"><span data-stu-id="875e8-115">Message</span></span>  

 <span data-ttu-id="875e8-116">La llamada a EndCommit en la CommittableTransaction con el identificador ='%1' inició una TransactionException con el siguiente mensaje: '%2'.</span><span class="sxs-lookup"><span data-stu-id="875e8-116">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="875e8-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="875e8-117">Details</span></span>  
  
|<span data-ttu-id="875e8-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="875e8-118">Data Item Name</span></span>|<span data-ttu-id="875e8-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="875e8-119">Data Item Type</span></span>|<span data-ttu-id="875e8-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="875e8-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="875e8-121">TransactionId</span><span class="sxs-lookup"><span data-stu-id="875e8-121">TransactionId</span></span>|<span data-ttu-id="875e8-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="875e8-122">xs:string</span></span>|<span data-ttu-id="875e8-123">Identificador de CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="875e8-123">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="875e8-124">Excepción</span><span class="sxs-lookup"><span data-stu-id="875e8-124">Exception</span></span>|<span data-ttu-id="875e8-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="875e8-125">xs:string</span></span>|<span data-ttu-id="875e8-126">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="875e8-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="875e8-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="875e8-127">AppDomain</span></span>|<span data-ttu-id="875e8-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="875e8-128">xs:string</span></span>|<span data-ttu-id="875e8-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="875e8-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
