---
title: Función ResetSecurity (referencia de API no administrada)
description: La función ResetSecurity asigna un token de suplantación para el subproceso actual.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e937690c184d810549e8ab11ef1fc2273a45c5f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115133"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="7c0ff-103">Función ResetSecurity</span><span class="sxs-lookup"><span data-stu-id="7c0ff-103">ResetSecurity function</span></span>
<span data-ttu-id="7c0ff-104">Asigna el token de suplantación proporcionado para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="7c0ff-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7c0ff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c0ff-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="7c0ff-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c0ff-106">Parameters</span></span>

`token`  
<span data-ttu-id="7c0ff-107">[in] El token de suplantación para asociar con el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="7c0ff-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="7c0ff-108">Este valor puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="7c0ff-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="7c0ff-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7c0ff-109">Return value</span></span>

<span data-ttu-id="7c0ff-110">Si la función se realiza correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="7c0ff-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="7c0ff-111">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="7c0ff-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="7c0ff-112">Para obtener información de error extendida, llame a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="7c0ff-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="7c0ff-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c0ff-113">Requirements</span></span>  
 <span data-ttu-id="7c0ff-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c0ff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0ff-115">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7c0ff-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7c0ff-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0ff-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c0ff-117">See also</span></span>

- [<span data-ttu-id="7c0ff-118">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="7c0ff-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
