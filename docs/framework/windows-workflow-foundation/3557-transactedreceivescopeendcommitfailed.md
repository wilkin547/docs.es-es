---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ea57cc60f9626763308267a98624c825f8312b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="5d535-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="5d535-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="5d535-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5d535-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d535-104">Id.</span><span class="sxs-lookup"><span data-stu-id="5d535-104">ID</span></span>|<span data-ttu-id="5d535-105">3557</span><span class="sxs-lookup"><span data-stu-id="5d535-105">3557</span></span>|  
|<span data-ttu-id="5d535-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d535-106">Keywords</span></span>|<span data-ttu-id="5d535-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="5d535-107">WFServices</span></span>|  
|<span data-ttu-id="5d535-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="5d535-108">Level</span></span>|<span data-ttu-id="5d535-109">Información</span><span class="sxs-lookup"><span data-stu-id="5d535-109">Information</span></span>|  
|<span data-ttu-id="5d535-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5d535-110">Channel</span></span>|<span data-ttu-id="5d535-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5d535-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d535-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d535-112">Description</span></span>  
 <span data-ttu-id="5d535-113">Indica que la llamada a EndCommit en un CommittableTransaction produjo una TransactionException.</span><span class="sxs-lookup"><span data-stu-id="5d535-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d535-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="5d535-114">Message</span></span>  
 <span data-ttu-id="5d535-115">La llamada a EndCommit en la CommittableTransaction con el identificador ='%1' inició una TransactionException con el siguiente mensaje: '%2'.</span><span class="sxs-lookup"><span data-stu-id="5d535-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d535-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d535-116">Details</span></span>  
  
|<span data-ttu-id="5d535-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5d535-117">Data Item Name</span></span>|<span data-ttu-id="5d535-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5d535-118">Data Item Type</span></span>|<span data-ttu-id="5d535-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d535-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d535-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="5d535-120">TransactionId</span></span>|<span data-ttu-id="5d535-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d535-121">xs:string</span></span>|<span data-ttu-id="5d535-122">Identificador de CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="5d535-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="5d535-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="5d535-123">Exception</span></span>|<span data-ttu-id="5d535-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d535-124">xs:string</span></span>|<span data-ttu-id="5d535-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="5d535-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="5d535-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d535-126">AppDomain</span></span>|<span data-ttu-id="5d535-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="5d535-127">xs:string</span></span>|<span data-ttu-id="5d535-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5d535-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
