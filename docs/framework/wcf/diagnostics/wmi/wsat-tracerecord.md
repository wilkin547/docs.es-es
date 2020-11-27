---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262221"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="12091-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="12091-102">WSAT_TraceRecord</span></span>

<span data-ttu-id="12091-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="12091-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12091-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12091-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="12091-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="12091-105">Methods</span></span>  

 <span data-ttu-id="12091-106">La clase WSAT_TraceRecord no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="12091-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="12091-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="12091-107">Properties</span></span>  

 <span data-ttu-id="12091-108">La clase WSAT_TraceRecord tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="12091-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="12091-109">Identificador de actividad</span><span class="sxs-lookup"><span data-stu-id="12091-109">ActivityID</span></span>  

 <span data-ttu-id="12091-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="12091-110">Data type: object</span></span>  
<span data-ttu-id="12091-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="12091-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12091-112">El id. de actividad del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="12091-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="12091-113">EventId</span><span class="sxs-lookup"><span data-stu-id="12091-113">EventID</span></span>  

 <span data-ttu-id="12091-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="12091-114">Data type: sint32</span></span>  
<span data-ttu-id="12091-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="12091-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12091-116">El id. de evento del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="12091-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="12091-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="12091-117">TraceRecord</span></span>  

 <span data-ttu-id="12091-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="12091-118">Data type: string</span></span>  
<span data-ttu-id="12091-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="12091-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="12091-120">Registro de seguimiento</span><span class="sxs-lookup"><span data-stu-id="12091-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12091-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12091-121">Requirements</span></span>  
  
|<span data-ttu-id="12091-122">MOF</span><span class="sxs-lookup"><span data-stu-id="12091-122">MOF</span></span>|<span data-ttu-id="12091-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="12091-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="12091-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="12091-124">Namespace</span></span>|<span data-ttu-id="12091-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="12091-125">Defined in root\ServiceModel</span></span>|
