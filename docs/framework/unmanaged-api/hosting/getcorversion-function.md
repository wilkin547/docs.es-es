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
ms.openlocfilehash: d0e922273a7d4e5b98c1321992e5e89e01adb437
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431498"
---
# <a name="getcorversion-function"></a><span data-ttu-id="9ae63-102">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="9ae63-102">GetCORVersion Function</span></span>
<span data-ttu-id="9ae63-103">Devuelve el número de versión de common language runtime (CLR) que se ejecuta en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="9ae63-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="9ae63-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ae63-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae63-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ae63-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ae63-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ae63-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="9ae63-107">Un puntero a un búfer en el que CLR devuelve una cadena que especifica la versión del runtime que está cargada actualmente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9ae63-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="9ae63-108">La cadena devuelta adopta el mismo formato como cadenas que se pasan al [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), por ejemplo, "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="9ae63-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="9ae63-109">Si el tiempo de ejecución aún no se han cargado en el proceso, la función devuelve la información de directorio adecuado para la versión más reciente del runtime instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9ae63-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9ae63-110">El número de caracteres (`WCHAR`s) que se pueden guardar en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="9ae63-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9ae63-111">Un puntero al número de caracteres devueltos realmente en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="9ae63-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="9ae63-112">Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="9ae63-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="9ae63-113">Si el número de caracteres es mayor, a continuación, la longitud de `pbuffer` , el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="9ae63-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ae63-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ae63-114">Requirements</span></span>  
 <span data-ttu-id="9ae63-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ae63-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae63-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ae63-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ae63-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ae63-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ae63-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae63-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae63-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ae63-119">See Also</span></span>  
 [<span data-ttu-id="9ae63-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9ae63-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
