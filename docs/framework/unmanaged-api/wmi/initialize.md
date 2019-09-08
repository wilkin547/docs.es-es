---
title: Función Initialize (referencia de la API no administrada)
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
ms.openlocfilehash: 1bc3688b30180bdcde0a87027955a789de749f90
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798440"
---
# <a name="initialize-function"></a><span data-ttu-id="5d659-103">Initialize (función)</span><span class="sxs-lookup"><span data-stu-id="5d659-103">Initialize function</span></span>

<span data-ttu-id="5d659-104">Realiza la inicialización de la WMI.</span><span class="sxs-lookup"><span data-stu-id="5d659-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5d659-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d659-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="5d659-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d659-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="5d659-107">de `true` para indicar que se permiten llamadas a QueryInterface en objetos WMI; `false` en caso contrario,.</span><span class="sxs-lookup"><span data-stu-id="5d659-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="5d659-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d659-108">Return value</span></span>

<span data-ttu-id="5d659-109">La función siempre devuelve `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="5d659-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="5d659-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d659-110">Requirements</span></span>

<span data-ttu-id="5d659-111">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d659-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="5d659-112">**Encabezado**: WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="5d659-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="5d659-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d659-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5d659-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d659-114">See also</span></span>

- [<span data-ttu-id="5d659-115">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="5d659-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
