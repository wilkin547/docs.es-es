---
title: Función SetSecurity (referencia de la API no administrada)
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
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120226"
---
# <a name="setsecurity-function"></a><span data-ttu-id="709b6-103">SetSecurity función)</span><span class="sxs-lookup"><span data-stu-id="709b6-103">SetSecurity function</span></span>

<span data-ttu-id="709b6-104">Recupera el token de suplantación asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="709b6-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="709b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="709b6-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="709b6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="709b6-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="709b6-107">enuncia Cuando la función devuelve un, contiene un puntero a un `boolean` que indica si el token se debe restablecer mediante una llamada a la función [ResetSecurity](resetsecurity.md) .</span><span class="sxs-lookup"><span data-stu-id="709b6-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="709b6-108">enuncia Cuando la función devuelve un objeto, contiene un puntero al identificador del token de suplantación asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="709b6-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="709b6-109">Su valor puede ser `null` si no hay ningún token asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="709b6-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="709b6-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="709b6-110">Return value</span></span>

<span data-ttu-id="709b6-111">Si la función se ejecuta correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="709b6-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="709b6-112">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="709b6-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="709b6-113">Para obtener información de error extendida, llame a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="709b6-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="709b6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="709b6-114">Requirements</span></span>

 <span data-ttu-id="709b6-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="709b6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="709b6-116">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="709b6-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="709b6-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="709b6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="709b6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="709b6-118">See also</span></span>

- [<span data-ttu-id="709b6-119">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="709b6-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
