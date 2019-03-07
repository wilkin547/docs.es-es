---
title: RunDll32ShimW (Función)
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 336fba6defc00eb87fcfa7e6b1aaafa0fcb15691
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494212"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="aabb6-102">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="aabb6-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="aabb6-103">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="aabb6-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="aabb6-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aabb6-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aabb6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aabb6-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aabb6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aabb6-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="aabb6-107">[in] Identificador de una ventana en la que se mostrará la salida del comando.</span><span class="sxs-lookup"><span data-stu-id="aabb6-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="aabb6-108">[in] Identificador de la biblioteca que contiene el comando.</span><span class="sxs-lookup"><span data-stu-id="aabb6-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="aabb6-109">[in] Una cadena que especifica el comando que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="aabb6-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="aabb6-110">[in] Un entero que especifica el modo de presentación para la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="aabb6-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aabb6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aabb6-111">Requirements</span></span>  
 <span data-ttu-id="aabb6-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aabb6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aabb6-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aabb6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aabb6-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aabb6-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aabb6-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aabb6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aabb6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="aabb6-116">See also</span></span>
- [<span data-ttu-id="aabb6-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="aabb6-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
