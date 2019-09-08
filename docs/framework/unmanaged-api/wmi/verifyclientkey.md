---
title: Función VerifyClientKey (referencia de la API no administrada)
description: La función VerifyClientKey garantiza que la clave de cliente tiene la seguridad correcta.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b674e959ab93cf76b84e2af41e875a50b7d115f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798192"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="dd5ab-103">VerifyClientKey función)</span><span class="sxs-lookup"><span data-stu-id="dd5ab-103">VerifyClientKey function</span></span>
<span data-ttu-id="dd5ab-104">Garantiza que la clave de cliente cuenta con la seguridad adecuada.</span><span class="sxs-lookup"><span data-stu-id="dd5ab-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="dd5ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd5ab-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="dd5ab-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd5ab-106">Return value</span></span>

<span data-ttu-id="dd5ab-107">Si la función se ejecuta correctamente, el valor devuelto es `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="dd5ab-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="dd5ab-108">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero definido en *WinError. h*.</span><span class="sxs-lookup"><span data-stu-id="dd5ab-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="dd5ab-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd5ab-109">Requirements</span></span>  
 <span data-ttu-id="dd5ab-110">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd5ab-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd5ab-111">**Encabezado**: WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="dd5ab-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="dd5ab-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dd5ab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd5ab-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd5ab-113">See also</span></span>

- [<span data-ttu-id="dd5ab-114">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="dd5ab-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
