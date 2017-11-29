---
title: "Initialize (función) (referencia de API no administrada)"
description: "La función de inicialización realiza la inicialización de WMI."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Initialize
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Initialize
helpviewer_keywords: Initialize function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ed0e0127608f9f80a2661067dd9a6025fd579a7
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="initialize-function"></a><span data-ttu-id="d719a-103">Initialize (función)</span><span class="sxs-lookup"><span data-stu-id="d719a-103">Initialize function</span></span>
<span data-ttu-id="d719a-104">Realiza la inicialización de WMI.</span><span class="sxs-lookup"><span data-stu-id="d719a-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d719a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d719a-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="d719a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d719a-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="d719a-107">[in] `true` para indicar que se permiten las llamadas a QueryInterface en objetos de WMI; `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="d719a-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="d719a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d719a-108">Return value</span></span>

<span data-ttu-id="d719a-109">La función siempre devuelve `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="d719a-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="d719a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d719a-110">Requirements</span></span>  
 <span data-ttu-id="d719a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d719a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d719a-112">**Encabezado:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="d719a-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="d719a-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d719a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d719a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d719a-114">See also</span></span>  
[<span data-ttu-id="d719a-115">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="d719a-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
