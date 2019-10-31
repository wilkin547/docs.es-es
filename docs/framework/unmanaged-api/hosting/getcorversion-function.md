---
title: GetCORVersion (Función)
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1283abaf6b08af1d842d8fe4469f7f6c15e38ec5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136418"
---
# <a name="getcorversion-function"></a><span data-ttu-id="f0c79-102">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="f0c79-102">GetCORVersion Function</span></span>
<span data-ttu-id="f0c79-103">Devuelve el número de versión del Common Language Runtime (CLR) que se ejecuta en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="f0c79-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="f0c79-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f0c79-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0c79-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="f0c79-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0c79-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="f0c79-107">Un puntero a un búfer en el que CLR devuelve una cadena que especifica la versión del Runtime que está cargada actualmente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f0c79-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="f0c79-108">La cadena devuelta tiene el mismo formato que las cadenas que se pasan a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), por ejemplo, "v 1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="f0c79-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="f0c79-109">Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del motor en tiempo de ejecución instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f0c79-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f0c79-110">Número de caracteres (`WCHAR`s) que se pueden mantener en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="f0c79-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f0c79-111">Puntero al número de caracteres devueltos realmente en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="f0c79-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="f0c79-112">Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="f0c79-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="f0c79-113">Si el número de caracteres es mayor que la longitud de `pbuffer`, el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="f0c79-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0c79-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0c79-114">Requirements</span></span>  
 <span data-ttu-id="f0c79-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0c79-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c79-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f0c79-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0c79-117">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f0c79-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0c79-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c79-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c79-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0c79-119">See also</span></span>

- [<span data-ttu-id="f0c79-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f0c79-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
