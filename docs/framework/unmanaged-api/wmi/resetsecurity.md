---
title: Función ResetSecurity (referencia de la API no administrada)
description: La función ResetSecurity asigna un token de suplantación al subproceso actual.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 95d91eac21e82e55af2f5e9ab181b770832f5ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120210"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="4abaf-103">ResetSecurity función)</span><span class="sxs-lookup"><span data-stu-id="4abaf-103">ResetSecurity function</span></span>
<span data-ttu-id="4abaf-104">Asigna el token de suplantación proporcionado para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="4abaf-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4abaf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4abaf-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="4abaf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4abaf-106">Parameters</span></span>

`token`  
<span data-ttu-id="4abaf-107">de El token de suplantación que se va a asociar al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="4abaf-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="4abaf-108">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="4abaf-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="4abaf-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4abaf-109">Return value</span></span>

<span data-ttu-id="4abaf-110">Si la función se ejecuta correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="4abaf-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="4abaf-111">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="4abaf-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="4abaf-112">Para obtener información de error extendida, llame a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="4abaf-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4abaf-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4abaf-113">Requirements</span></span>  
 <span data-ttu-id="4abaf-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4abaf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4abaf-115">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="4abaf-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4abaf-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4abaf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4abaf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4abaf-117">See also</span></span>

- [<span data-ttu-id="4abaf-118">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="4abaf-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
