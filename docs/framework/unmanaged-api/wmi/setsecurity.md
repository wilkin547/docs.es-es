---
title: Función SetSecurity (Referencia de API no administrada)
description: La función SetSecurity recupera el token de suplantación del subproceso actual.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176739"
---
# <a name="setsecurity-function"></a><span data-ttu-id="a0d14-103">Función SetSecurity</span><span class="sxs-lookup"><span data-stu-id="a0d14-103">SetSecurity function</span></span>

<span data-ttu-id="a0d14-104">Recupera el token de suplantación asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a0d14-104">Retrieves the impersonation token associated with the current thread.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a0d14-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0d14-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a><span data-ttu-id="a0d14-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0d14-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="a0d14-107">[fuera] Cuando se devuelve la función, contiene un puntero a un `boolean` que indica si el token se debe restablecer mediante una llamada a la [ResetSecurity](resetsecurity.md) función.</span><span class="sxs-lookup"><span data-stu-id="a0d14-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="a0d14-108">[fuera] Cuando se devuelve la función, contiene un puntero al identificador del token de suplantación asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a0d14-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="a0d14-109">Su valor `null` puede ser si no hay ningún token asociado con el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a0d14-109">Its value can be `null` if there is no token associated with the current thread.</span></span>

## <a name="return-value"></a><span data-ttu-id="a0d14-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a0d14-110">Return value</span></span>

<span data-ttu-id="a0d14-111">Si la función se realiza `S_OK` correctamente, el valor devuelto es (0).</span><span class="sxs-lookup"><span data-stu-id="a0d14-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="a0d14-112">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="a0d14-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="a0d14-113">Para obtener información de error extendida, llame a la [función GetErrorInfo.](geterrorinfo.md)</span><span class="sxs-lookup"><span data-stu-id="a0d14-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0d14-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0d14-114">Requirements</span></span>

 <span data-ttu-id="a0d14-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0d14-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="a0d14-116">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a0d14-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="a0d14-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a0d14-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a0d14-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0d14-118">See also</span></span>

- [<span data-ttu-id="a0d14-119">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="a0d14-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
