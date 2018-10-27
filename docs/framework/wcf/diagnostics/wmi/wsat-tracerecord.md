---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194779"
---
# <a name="wsattracerecord"></a><span data-ttu-id="805e8-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="805e8-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="805e8-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="805e8-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="805e8-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="805e8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="805e8-105">Methods</span></span>  
 <span data-ttu-id="805e8-106">La clase WSAT_TraceRecord no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="805e8-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="805e8-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="805e8-107">Properties</span></span>  
 <span data-ttu-id="805e8-108">La clase WSAT_TraceRecord tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="805e8-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="805e8-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="805e8-109">ActivityID</span></span>  
 <span data-ttu-id="805e8-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="805e8-110">Data type: object</span></span>  
<span data-ttu-id="805e8-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="805e8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="805e8-112">El id. de actividad del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="805e8-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="805e8-113">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="805e8-113">EventID</span></span>  
 <span data-ttu-id="805e8-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="805e8-114">Data type: sint32</span></span>  
<span data-ttu-id="805e8-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="805e8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="805e8-116">El id. de evento del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="805e8-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="805e8-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="805e8-117">TraceRecord</span></span>  
 <span data-ttu-id="805e8-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="805e8-118">Data type: string</span></span>  
<span data-ttu-id="805e8-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="805e8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="805e8-120">Registro de seguimiento</span><span class="sxs-lookup"><span data-stu-id="805e8-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="805e8-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="805e8-121">Requirements</span></span>  
  
|<span data-ttu-id="805e8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="805e8-122">MOF</span></span>|<span data-ttu-id="805e8-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="805e8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="805e8-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="805e8-124">Namespace</span></span>|<span data-ttu-id="805e8-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="805e8-125">Defined in root\ServiceModel</span></span>|
