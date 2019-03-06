---
title: Función SetSecurity (referencia de API no administrada)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7200e3a19fcadabb5e149c38b620b3f60907c392
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377422"
---
# <a name="setsecurity-function"></a><span data-ttu-id="c3628-103">Función SetSecurity</span><span class="sxs-lookup"><span data-stu-id="c3628-103">SetSecurity function</span></span>

<span data-ttu-id="c3628-104">Recupera el token de suplantación asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c3628-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c3628-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3628-105">Syntax</span></span>

```
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="c3628-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3628-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="c3628-107">[out] Cuando la función devuelve, contiene un puntero a un `boolean` que indica si se debe restablecer el token mediante una llamada a la [ResetSecurity](resetsecurity.md) función.</span><span class="sxs-lookup"><span data-stu-id="c3628-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="c3628-108">[out] La función devuelve, contiene un puntero al identificador del token de suplantación asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c3628-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="c3628-109">Su valor puede ser `null` si no hay ningún testigo asociado con el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c3628-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="c3628-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c3628-110">Return value</span></span>

<span data-ttu-id="c3628-111">Si la función se realiza correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="c3628-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="c3628-112">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="c3628-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="c3628-113">Para obtener información de error extendida, llame a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="c3628-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3628-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3628-114">Requirements</span></span>

 <span data-ttu-id="c3628-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3628-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="c3628-116">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c3628-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="c3628-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3628-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c3628-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3628-118">See also</span></span>

- [<span data-ttu-id="c3628-119">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c3628-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)