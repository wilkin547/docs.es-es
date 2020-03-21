---
title: Función VerifyClientKey (Referencia de API no administrada)
description: La función VerifyClientKey garantiza que la clave de cliente tenga la seguridad correcta.
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
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176713"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="29c0a-103">Función VerifyClientKey</span><span class="sxs-lookup"><span data-stu-id="29c0a-103">VerifyClientKey function</span></span>
<span data-ttu-id="29c0a-104">Garantiza que la clave de cliente cuenta con la seguridad adecuada.</span><span class="sxs-lookup"><span data-stu-id="29c0a-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="29c0a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29c0a-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="29c0a-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="29c0a-106">Return value</span></span>

<span data-ttu-id="29c0a-107">Si la función se realiza `ERROR_SUCCESS` correctamente, el valor devuelto es (0).</span><span class="sxs-lookup"><span data-stu-id="29c0a-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="29c0a-108">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero definido en *WinError.h*.</span><span class="sxs-lookup"><span data-stu-id="29c0a-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="29c0a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29c0a-109">Requirements</span></span>  
 <span data-ttu-id="29c0a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c0a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c0a-111">**Encabezado:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="29c0a-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="29c0a-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="29c0a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c0a-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29c0a-113">See also</span></span>

- [<span data-ttu-id="29c0a-114">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="29c0a-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
