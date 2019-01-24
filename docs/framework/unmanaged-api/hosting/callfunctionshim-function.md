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
ms.openlocfilehash: 39223e10b0f75eefb83f3b9a83c5f030318cd715
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738935"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="1dff7-102">CallFunctionShim (Función)</span><span class="sxs-lookup"><span data-stu-id="1dff7-102">CallFunctionShim Function</span></span>
<span data-ttu-id="1dff7-103">Realiza una llamada a la función que tiene el nombre especificado y los parámetros de la biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="1dff7-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="1dff7-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1dff7-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dff7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dff7-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1dff7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1dff7-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="1dff7-107">[in] El nombre de la biblioteca que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="1dff7-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="1dff7-108">[in] El nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="1dff7-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="1dff7-109">[in] El primer argumento para pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="1dff7-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="1dff7-110">[in] El segundo argumento para pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="1dff7-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="1dff7-111">[in] La versión de la biblioteca que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="1dff7-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="1dff7-112">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="1dff7-112">[in] Reserved for future use.</span></span> <span data-ttu-id="1dff7-113">Pasar cero en este parámetro.</span><span class="sxs-lookup"><span data-stu-id="1dff7-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dff7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1dff7-114">Requirements</span></span>  
 <span data-ttu-id="1dff7-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dff7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dff7-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1dff7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1dff7-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1dff7-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1dff7-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dff7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dff7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dff7-119">See also</span></span>
- [<span data-ttu-id="1dff7-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="1dff7-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
