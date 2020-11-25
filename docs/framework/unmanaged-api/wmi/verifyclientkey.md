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
ms.openlocfilehash: 26cffe9936f2e01078b6f54e8499b58519f1018e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729426"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="82151-103">VerifyClientKey función)</span><span class="sxs-lookup"><span data-stu-id="82151-103">VerifyClientKey function</span></span>

<span data-ttu-id="82151-104">Garantiza que la clave de cliente cuenta con la seguridad adecuada.</span><span class="sxs-lookup"><span data-stu-id="82151-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="82151-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82151-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="82151-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="82151-106">Return value</span></span>

<span data-ttu-id="82151-107">Si la función se ejecuta correctamente, el valor devuelto es `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="82151-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="82151-108">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero definido en *WinError. h*.</span><span class="sxs-lookup"><span data-stu-id="82151-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="82151-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82151-109">Requirements</span></span>  

 <span data-ttu-id="82151-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82151-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82151-111">**Encabezado:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="82151-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="82151-112">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="82151-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82151-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82151-113">See also</span></span>

- [<span data-ttu-id="82151-114">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="82151-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
