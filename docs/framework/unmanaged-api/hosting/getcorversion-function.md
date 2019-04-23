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
ms.openlocfilehash: f66e00c3334aecdf8c653f57e28d1b327c4170e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094076"
---
# <a name="getcorversion-function"></a><span data-ttu-id="ab2b9-102">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="ab2b9-102">GetCORVersion Function</span></span>
<span data-ttu-id="ab2b9-103">Devuelve el número de versión de common language runtime (CLR) que se está ejecutando en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="ab2b9-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="ab2b9-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab2b9-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab2b9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab2b9-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ab2b9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab2b9-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="ab2b9-107">Un puntero a un búfer en el que el CLR devuelve una cadena que especifica la versión del runtime que está cargada actualmente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ab2b9-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="ab2b9-108">La cadena devuelta adopta el mismo formato que cadenas se pasan al [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), por ejemplo, "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="ab2b9-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="ab2b9-109">Si el tiempo de ejecución aún no se han cargado en el proceso, la función devuelve la información de directorio adecuado para la versión más reciente del runtime instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ab2b9-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ab2b9-110">El número de caracteres (`WCHAR`s) que se pueden mantener en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="ab2b9-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ab2b9-111">Un puntero al número de caracteres devueltos realmente en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="ab2b9-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="ab2b9-112">Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="ab2b9-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="ab2b9-113">Si el número de caracteres es mayor, a continuación, la longitud de `pbuffer` , el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="ab2b9-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab2b9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab2b9-114">Requirements</span></span>  
 <span data-ttu-id="ab2b9-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab2b9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab2b9-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ab2b9-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab2b9-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab2b9-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab2b9-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab2b9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2b9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab2b9-119">See also</span></span>

- [<span data-ttu-id="ab2b9-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="ab2b9-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
