---
description: 'Más información acerca de: WSAT_TraceRecord'
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 67202c5d2910783c40b934d2da6108e6b514a728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756882"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="cb1f3-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cb1f3-103">WSAT_TraceRecord</span></span>

<span data-ttu-id="cb1f3-104">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cb1f3-104">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1f3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb1f3-105">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cb1f3-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="cb1f3-106">Methods</span></span>  

 <span data-ttu-id="cb1f3-107">La clase WSAT_TraceRecord no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="cb1f3-107">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cb1f3-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cb1f3-108">Properties</span></span>  

 <span data-ttu-id="cb1f3-109">La clase WSAT_TraceRecord tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb1f3-109">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="cb1f3-110">Identificador de actividad</span><span class="sxs-lookup"><span data-stu-id="cb1f3-110">ActivityID</span></span>  

 <span data-ttu-id="cb1f3-111">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="cb1f3-111">Data type: object</span></span>  
<span data-ttu-id="cb1f3-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="cb1f3-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb1f3-113">El id. de actividad del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="cb1f3-113">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="cb1f3-114">EventId</span><span class="sxs-lookup"><span data-stu-id="cb1f3-114">EventID</span></span>  

 <span data-ttu-id="cb1f3-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="cb1f3-115">Data type: sint32</span></span>  
<span data-ttu-id="cb1f3-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="cb1f3-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb1f3-117">El id. de evento del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="cb1f3-117">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="cb1f3-118">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="cb1f3-118">TraceRecord</span></span>  

 <span data-ttu-id="cb1f3-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="cb1f3-119">Data type: string</span></span>  
<span data-ttu-id="cb1f3-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="cb1f3-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="cb1f3-121">Registro de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cb1f3-121">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb1f3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb1f3-122">Requirements</span></span>  
  
|<span data-ttu-id="cb1f3-123">MOF</span><span class="sxs-lookup"><span data-stu-id="cb1f3-123">MOF</span></span>|<span data-ttu-id="cb1f3-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cb1f3-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cb1f3-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="cb1f3-125">Namespace</span></span>|<span data-ttu-id="cb1f3-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cb1f3-126">Defined in root\ServiceModel</span></span>|
