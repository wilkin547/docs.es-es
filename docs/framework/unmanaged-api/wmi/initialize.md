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
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127391"
---
# <a name="initialize-function"></a><span data-ttu-id="d8a24-103">Initialize (función)</span><span class="sxs-lookup"><span data-stu-id="d8a24-103">Initialize function</span></span>

<span data-ttu-id="d8a24-104">Realiza la inicialización de la WMI.</span><span class="sxs-lookup"><span data-stu-id="d8a24-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d8a24-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8a24-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="d8a24-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8a24-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="d8a24-107">[in] `true` para indicar que se permiten llamadas a QueryInterface en objetos WMI; de lo contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="d8a24-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="d8a24-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8a24-108">Return value</span></span>

<span data-ttu-id="d8a24-109">La función siempre devuelve `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="d8a24-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="d8a24-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8a24-110">Requirements</span></span>

<span data-ttu-id="d8a24-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8a24-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d8a24-112">**Encabezado:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="d8a24-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="d8a24-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d8a24-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d8a24-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8a24-114">See also</span></span>

- [<span data-ttu-id="d8a24-115">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="d8a24-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
