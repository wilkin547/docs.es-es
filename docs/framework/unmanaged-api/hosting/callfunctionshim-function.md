---
title: CallFunctionShim (Función)
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31d93ac427ec67726c9456d623aeb683c9029ccd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773761"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="f2f2a-102">CallFunctionShim (Función)</span><span class="sxs-lookup"><span data-stu-id="f2f2a-102">CallFunctionShim Function</span></span>
<span data-ttu-id="f2f2a-103">Realiza una llamada a la función que tiene el nombre especificado y los parámetros de la biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="f2f2a-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f2a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2f2a-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2f2a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2f2a-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="f2f2a-107">[in] El nombre de la biblioteca que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="f2f2a-108">[in] El nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="f2f2a-109">[in] El primer argumento para pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="f2f2a-110">[in] El segundo argumento para pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="f2f2a-111">[in] La versión de la biblioteca que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f2f2a-112">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-112">[in] Reserved for future use.</span></span> <span data-ttu-id="f2f2a-113">Pasar cero en este parámetro.</span><span class="sxs-lookup"><span data-stu-id="f2f2a-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f2a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2f2a-114">Requirements</span></span>  
 <span data-ttu-id="f2f2a-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2f2a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2f2a-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2f2a-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2f2a-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2f2a-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2f2a-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f2a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f2a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2f2a-119">See also</span></span>

- [<span data-ttu-id="f2f2a-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f2f2a-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
