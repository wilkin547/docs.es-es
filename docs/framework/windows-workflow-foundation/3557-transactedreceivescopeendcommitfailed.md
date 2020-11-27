---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 4a4979047481687ef0d5c9d5891dec8f2826beed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263664"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="d09e9-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="d09e9-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>

## <a name="properties"></a><span data-ttu-id="d09e9-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d09e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d09e9-104">ID</span><span class="sxs-lookup"><span data-stu-id="d09e9-104">ID</span></span>|<span data-ttu-id="d09e9-105">3557</span><span class="sxs-lookup"><span data-stu-id="d09e9-105">3557</span></span>|  
|<span data-ttu-id="d09e9-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d09e9-106">Keywords</span></span>|<span data-ttu-id="d09e9-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d09e9-107">WFServices</span></span>|  
|<span data-ttu-id="d09e9-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d09e9-108">Level</span></span>|<span data-ttu-id="d09e9-109">Información</span><span class="sxs-lookup"><span data-stu-id="d09e9-109">Information</span></span>|  
|<span data-ttu-id="d09e9-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d09e9-110">Channel</span></span>|<span data-ttu-id="d09e9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d09e9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d09e9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d09e9-112">Description</span></span>  

 <span data-ttu-id="d09e9-113">Indica que la llamada a EndCommit en un CommittableTransaction produjo una TransactionException.</span><span class="sxs-lookup"><span data-stu-id="d09e9-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d09e9-114">Message</span><span class="sxs-lookup"><span data-stu-id="d09e9-114">Message</span></span>  

 <span data-ttu-id="d09e9-115">La llamada a EndCommit en la CommittableTransaction con el identificador ='%1' inició una TransactionException con el siguiente mensaje: '%2'.</span><span class="sxs-lookup"><span data-stu-id="d09e9-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d09e9-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d09e9-116">Details</span></span>  
  
|<span data-ttu-id="d09e9-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d09e9-117">Data Item Name</span></span>|<span data-ttu-id="d09e9-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d09e9-118">Data Item Type</span></span>|<span data-ttu-id="d09e9-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d09e9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d09e9-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="d09e9-120">TransactionId</span></span>|<span data-ttu-id="d09e9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d09e9-121">xs:string</span></span>|<span data-ttu-id="d09e9-122">Identificador de CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="d09e9-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="d09e9-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="d09e9-123">Exception</span></span>|<span data-ttu-id="d09e9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d09e9-124">xs:string</span></span>|<span data-ttu-id="d09e9-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="d09e9-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="d09e9-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d09e9-126">AppDomain</span></span>|<span data-ttu-id="d09e9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d09e9-127">xs:string</span></span>|<span data-ttu-id="d09e9-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d09e9-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
