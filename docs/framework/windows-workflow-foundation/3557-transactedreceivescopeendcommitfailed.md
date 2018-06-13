---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 444fa2e51322edd793f709fd3f92c5f9fe826522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512166"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="273aa-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="273aa-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="273aa-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="273aa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="273aa-104">Id.</span><span class="sxs-lookup"><span data-stu-id="273aa-104">ID</span></span>|<span data-ttu-id="273aa-105">3557</span><span class="sxs-lookup"><span data-stu-id="273aa-105">3557</span></span>|  
|<span data-ttu-id="273aa-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="273aa-106">Keywords</span></span>|<span data-ttu-id="273aa-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="273aa-107">WFServices</span></span>|  
|<span data-ttu-id="273aa-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="273aa-108">Level</span></span>|<span data-ttu-id="273aa-109">Información</span><span class="sxs-lookup"><span data-stu-id="273aa-109">Information</span></span>|  
|<span data-ttu-id="273aa-110">Canal</span><span class="sxs-lookup"><span data-stu-id="273aa-110">Channel</span></span>|<span data-ttu-id="273aa-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="273aa-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="273aa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="273aa-112">Description</span></span>  
 <span data-ttu-id="273aa-113">Indica que la llamada a EndCommit en un CommittableTransaction produjo una TransactionException.</span><span class="sxs-lookup"><span data-stu-id="273aa-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="273aa-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="273aa-114">Message</span></span>  
 <span data-ttu-id="273aa-115">La llamada a EndCommit en la CommittableTransaction con el identificador ='%1' inició una TransactionException con el siguiente mensaje: '%2'.</span><span class="sxs-lookup"><span data-stu-id="273aa-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="273aa-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="273aa-116">Details</span></span>  
  
|<span data-ttu-id="273aa-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="273aa-117">Data Item Name</span></span>|<span data-ttu-id="273aa-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="273aa-118">Data Item Type</span></span>|<span data-ttu-id="273aa-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="273aa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="273aa-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="273aa-120">TransactionId</span></span>|<span data-ttu-id="273aa-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="273aa-121">xs:string</span></span>|<span data-ttu-id="273aa-122">Identificador de CommittableTransaction.</span><span class="sxs-lookup"><span data-stu-id="273aa-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="273aa-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="273aa-123">Exception</span></span>|<span data-ttu-id="273aa-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="273aa-124">xs:string</span></span>|<span data-ttu-id="273aa-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="273aa-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="273aa-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="273aa-126">AppDomain</span></span>|<span data-ttu-id="273aa-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="273aa-127">xs:string</span></span>|<span data-ttu-id="273aa-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="273aa-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
