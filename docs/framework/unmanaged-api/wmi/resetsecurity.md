---
title: "Función ResetSecurity (referencia de API no administrada)"
description: "La función ResetSecurity asigna un token de suplantación al subproceso actual."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ResetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ResetSecurity
helpviewer_keywords: ResetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bacee65633d25e705d978d3902a6804516a88bf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="resetsecurity-function"></a><span data-ttu-id="524b9-103">ResetSecurity (función)</span><span class="sxs-lookup"><span data-stu-id="524b9-103">ResetSecurity function</span></span>
<span data-ttu-id="524b9-104">Asigna el token de suplantación proporcionado para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="524b9-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="524b9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="524b9-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="524b9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="524b9-106">Parameters</span></span>

`token`  
<span data-ttu-id="524b9-107">[in] El token de suplantación para asociar con el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="524b9-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="524b9-108">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="524b9-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="524b9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="524b9-109">Return value</span></span>

<span data-ttu-id="524b9-110">Si la función se realiza correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="524b9-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="524b9-111">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="524b9-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="524b9-112">Para obtener información de error extendida, llame a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="524b9-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="524b9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="524b9-113">Requirements</span></span>  
 <span data-ttu-id="524b9-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="524b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="524b9-115">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="524b9-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="524b9-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="524b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524b9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="524b9-117">See also</span></span>  
[<span data-ttu-id="524b9-118">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="524b9-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
