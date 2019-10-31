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
ms.openlocfilehash: 0a0680651eb192e2798ede00048599c5130e63f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107355"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="abbff-103">VerifyClientKey función)</span><span class="sxs-lookup"><span data-stu-id="abbff-103">VerifyClientKey function</span></span>
<span data-ttu-id="abbff-104">Garantiza que la clave de cliente cuenta con la seguridad adecuada.</span><span class="sxs-lookup"><span data-stu-id="abbff-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="abbff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abbff-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="abbff-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="abbff-106">Return value</span></span>

<span data-ttu-id="abbff-107">Si la función se ejecuta correctamente, el valor devuelto es `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="abbff-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="abbff-108">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero definido en *WinError. h*.</span><span class="sxs-lookup"><span data-stu-id="abbff-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="abbff-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abbff-109">Requirements</span></span>  
 <span data-ttu-id="abbff-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abbff-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abbff-111">**Encabezado:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="abbff-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="abbff-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="abbff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbff-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="abbff-113">See also</span></span>

- [<span data-ttu-id="abbff-114">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="abbff-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
