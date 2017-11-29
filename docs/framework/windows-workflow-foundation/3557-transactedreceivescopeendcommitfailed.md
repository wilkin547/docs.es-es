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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1f9f1066f1948411d584a2dee1af2129aa3a103
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="4d324-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="4d324-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="4d324-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4d324-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d324-104">Id.</span><span class="sxs-lookup"><span data-stu-id="4d324-104">ID</span></span>|<span data-ttu-id="4d324-105">3557</span><span class="sxs-lookup"><span data-stu-id="4d324-105">3557</span></span>|  
|<span data-ttu-id="4d324-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4d324-106">Keywords</span></span>|<span data-ttu-id="4d324-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="4d324-107">WFServices</span></span>|  
|<span data-ttu-id="4d324-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="4d324-108">Level</span></span>|<span data-ttu-id="4d324-109">Información</span><span class="sxs-lookup"><span data-stu-id="4d324-109">Information</span></span>|  
|<span data-ttu-id="4d324-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4d324-110">Channel</span></span>|<span data-ttu-id="4d324-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4d324-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4d324-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d324-112">Description</span></span>  
 <span data-ttu-id="4d324-113">Indica que la llamada a EndCommit en un CommittableTransaction produjo una TransactionException.</span><span class="sxs-lookup"><span data-stu-id="4d324-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4d324-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4d324-114">Message</span></span>  
 <span data-ttu-id="4d324-115">La llamada a EndCommit en la CommittableTransaction con el identificador ='%1' inició una TransactionException con el siguiente mensaje: '%2'.</span><span class="sxs-lookup"><span data-stu-id="4d324-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4d324-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="4d324-116">Details</span></span>  
  
|<span data-ttu-id="4d324-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4d324-117">Data Item Name</span></span>|<span data-ttu-id="4d324-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4d324-118">Data Item Type</span></span>|<span data-ttu-id="4d324-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d324-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4d324-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="4d324-120">TransactionId</span></span>|<span data-ttu-id="4d324-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d324-121">xs:string</span></span>|<span data-ttu-id="4d324-122">Identificador de CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="4d324-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="4d324-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="4d324-123">Exception</span></span>|<span data-ttu-id="4d324-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d324-124">xs:string</span></span>|<span data-ttu-id="4d324-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="4d324-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="4d324-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4d324-126">AppDomain</span></span>|<span data-ttu-id="4d324-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4d324-127">xs:string</span></span>|<span data-ttu-id="4d324-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4d324-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
