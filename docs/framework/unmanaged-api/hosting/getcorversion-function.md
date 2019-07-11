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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe5525fc29bc01bb84f7f2997d115eec12d72b13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736276"
---
# <a name="getcorversion-function"></a><span data-ttu-id="39e2d-102">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="39e2d-102">GetCORVersion Function</span></span>
<span data-ttu-id="39e2d-103">Devuelve el número de versión de common language runtime (CLR) que se está ejecutando en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="39e2d-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="39e2d-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="39e2d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39e2d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39e2d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="39e2d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39e2d-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="39e2d-107">Un puntero a un búfer en el que el CLR devuelve una cadena que especifica la versión del runtime que está cargada actualmente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="39e2d-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="39e2d-108">La cadena devuelta adopta el mismo formato que cadenas se pasan al [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), por ejemplo, "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="39e2d-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="39e2d-109">Si el tiempo de ejecución aún no se han cargado en el proceso, la función devuelve la información de directorio adecuado para la versión más reciente del runtime instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="39e2d-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="39e2d-110">El número de caracteres (`WCHAR`s) que se pueden mantener en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="39e2d-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="39e2d-111">Un puntero al número de caracteres devueltos realmente en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="39e2d-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="39e2d-112">Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="39e2d-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="39e2d-113">Si el número de caracteres es mayor, a continuación, la longitud de `pbuffer` , el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="39e2d-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39e2d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39e2d-114">Requirements</span></span>  
 <span data-ttu-id="39e2d-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39e2d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39e2d-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39e2d-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39e2d-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39e2d-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39e2d-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39e2d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e2d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="39e2d-119">See also</span></span>

- [<span data-ttu-id="39e2d-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="39e2d-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
