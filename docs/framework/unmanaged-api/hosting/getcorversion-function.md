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
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178191"
---
# <a name="getcorversion-function"></a><span data-ttu-id="04783-102">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="04783-102">GetCORVersion Function</span></span>
<span data-ttu-id="04783-103">Devuelve el número de versión de Common Language Runtime (CLR) que se ejecuta en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="04783-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="04783-104">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="04783-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04783-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04783-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="04783-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04783-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="04783-107">Puntero a un búfer en el que CLR devuelve una cadena que especifica la versión del tiempo de ejecución que se carga actualmente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="04783-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="04783-108">La cadena devuelta toma la misma forma que las cadenas pasadas a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), por ejemplo, "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="04783-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="04783-109">Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del tiempo de ejecución instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="04783-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="04783-110">El número de`WCHAR`caracteres ( s) que se pueden mantener en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="04783-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="04783-111">Puntero al número de caracteres `pbuffer`devueltos en .</span><span class="sxs-lookup"><span data-stu-id="04783-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="04783-112">Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="04783-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="04783-113">Si el número de caracteres `pbuffer` es mayor, a continuación, la longitud de , el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="04783-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04783-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04783-114">Requirements</span></span>  
 <span data-ttu-id="04783-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04783-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04783-116">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="04783-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04783-117">**Biblioteca:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="04783-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04783-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04783-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04783-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04783-119">See also</span></span>

- [<span data-ttu-id="04783-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="04783-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
