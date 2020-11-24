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
ms.openlocfilehash: e7ef3f300c8cfa0c275d15913e171abe09385eea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681215"
---
# <a name="getcorversion-function"></a><span data-ttu-id="5b82c-102">GetCORVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="5b82c-102">GetCORVersion Function</span></span>

<span data-ttu-id="5b82c-103">Devuelve el número de versión del Common Language Runtime (CLR) que se ejecuta en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="5b82c-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="5b82c-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5b82c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b82c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b82c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="5b82c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5b82c-106">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="5b82c-107">Un puntero a un búfer en el que CLR devuelve una cadena que especifica la versión del Runtime que está cargada actualmente en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5b82c-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="5b82c-108">La cadena devuelta tiene el mismo formato que las cadenas que se pasan a [CorBindToRuntimeEx](corbindtoruntimeex-function.md), por ejemplo, "v 1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="5b82c-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="5b82c-109">Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del motor en tiempo de ejecución instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5b82c-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="5b82c-110">Número de caracteres `WCHAR` que se pueden mantener en `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="5b82c-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="5b82c-111">Puntero al número de caracteres realmente devueltos en `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="5b82c-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="5b82c-112">Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="5b82c-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="5b82c-113">Si el número de caracteres es mayor que la longitud de `pbuffer` , el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="5b82c-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b82c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b82c-114">Requirements</span></span>  

 <span data-ttu-id="5b82c-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b82c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b82c-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5b82c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b82c-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b82c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b82c-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b82c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b82c-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b82c-119">See also</span></span>

- [<span data-ttu-id="5b82c-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="5b82c-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
