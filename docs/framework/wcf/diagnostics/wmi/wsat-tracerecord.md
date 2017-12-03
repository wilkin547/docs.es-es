---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="54b2d-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="54b2d-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="54b2d-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="54b2d-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54b2d-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="54b2d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="54b2d-105">Methods</span></span>  
 <span data-ttu-id="54b2d-106">La clase WSAT_TraceRecord no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="54b2d-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="54b2d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="54b2d-107">Properties</span></span>  
 <span data-ttu-id="54b2d-108">La clase WSAT_TraceRecord tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="54b2d-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="54b2d-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="54b2d-109">ActivityID</span></span>  
 <span data-ttu-id="54b2d-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="54b2d-110">Data type: object</span></span>  
<span data-ttu-id="54b2d-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="54b2d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="54b2d-112">El id. de actividad del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="54b2d-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="54b2d-113">EventID</span><span class="sxs-lookup"><span data-stu-id="54b2d-113">EventID</span></span>  
 <span data-ttu-id="54b2d-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="54b2d-114">Data type: sint32</span></span>  
<span data-ttu-id="54b2d-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="54b2d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="54b2d-116">El id. de evento del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="54b2d-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="54b2d-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="54b2d-117">TraceRecord</span></span>  
 <span data-ttu-id="54b2d-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="54b2d-118">Data type: string</span></span>  
<span data-ttu-id="54b2d-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="54b2d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="54b2d-120">Registro de seguimiento</span><span class="sxs-lookup"><span data-stu-id="54b2d-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54b2d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54b2d-121">Requirements</span></span>  
  
|<span data-ttu-id="54b2d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="54b2d-122">MOF</span></span>|<span data-ttu-id="54b2d-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="54b2d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="54b2d-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="54b2d-124">Namespace</span></span>|<span data-ttu-id="54b2d-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="54b2d-125">Defined in root\ServiceModel</span></span>|
