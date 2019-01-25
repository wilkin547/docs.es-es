---
title: Initialize (función) (referencia de API no administrada)
description: La función Initialize realiza la inicialización de WMI.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f56ce2da5cc1b79fded3788ddb9631d2c8a2fa7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693657"
---
# <a name="initialize-function"></a><span data-ttu-id="0fe6f-103">Initialize (función)</span><span class="sxs-lookup"><span data-stu-id="0fe6f-103">Initialize function</span></span>
<span data-ttu-id="0fe6f-104">Realiza la inicialización de la WMI.</span><span class="sxs-lookup"><span data-stu-id="0fe6f-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0fe6f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fe6f-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="0fe6f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fe6f-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="0fe6f-107">[in] `true` para indicar que se permiten las llamadas a QueryInterface en objetos WMI; `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="0fe6f-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="0fe6f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0fe6f-108">Return value</span></span>

<span data-ttu-id="0fe6f-109">La función siempre devuelve `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="0fe6f-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="0fe6f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fe6f-110">Requirements</span></span>  
 <span data-ttu-id="0fe6f-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fe6f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fe6f-112">**Encabezado**: WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="0fe6f-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="0fe6f-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0fe6f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe6f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fe6f-114">See also</span></span>
- [<span data-ttu-id="0fe6f-115">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="0fe6f-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
