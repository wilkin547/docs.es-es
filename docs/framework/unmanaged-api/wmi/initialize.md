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
ms.openlocfilehash: ca8e87157a7adf45f35608aeba1067f2d66c8972
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081611"
---
# <a name="initialize-function"></a><span data-ttu-id="9d132-103">Initialize (función)</span><span class="sxs-lookup"><span data-stu-id="9d132-103">Initialize function</span></span>
<span data-ttu-id="9d132-104">Realiza la inicialización de la WMI.</span><span class="sxs-lookup"><span data-stu-id="9d132-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9d132-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d132-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="9d132-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d132-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="9d132-107">[in] `true` para indicar que se permiten las llamadas a QueryInterface en objetos WMI; `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="9d132-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="9d132-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9d132-108">Return value</span></span>

<span data-ttu-id="9d132-109">La función siempre devuelve `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="9d132-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="9d132-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d132-110">Requirements</span></span>  
 <span data-ttu-id="9d132-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d132-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d132-112">**Encabezado**: WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="9d132-112">**Header:** WMINet_Utils.def</span></span>  
  
 **<span data-ttu-id="9d132-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9d132-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9d132-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d132-114">See also</span></span>

- [<span data-ttu-id="9d132-115">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="9d132-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
