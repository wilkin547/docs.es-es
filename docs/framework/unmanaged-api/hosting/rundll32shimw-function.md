---
title: "RunDll32ShimW (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RunDll32ShimW
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: RunDll32ShimW
helpviewer_keywords: RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a046ed8d540b27bfb73a6e94f148d41f8ac7b264
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="3b007-102">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="3b007-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="3b007-103">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="3b007-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="3b007-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b007-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b007-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b007-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b007-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b007-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="3b007-107">[in] Identificador de una ventana en la que se mostrará la salida del comando.</span><span class="sxs-lookup"><span data-stu-id="3b007-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="3b007-108">[in] Identificador de la biblioteca que contiene el comando.</span><span class="sxs-lookup"><span data-stu-id="3b007-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="3b007-109">[in] Una cadena que especifica que se ejecute el comando.</span><span class="sxs-lookup"><span data-stu-id="3b007-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="3b007-110">[in] Un entero que especifica el modo de presentación de la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="3b007-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b007-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b007-111">Requirements</span></span>  
 <span data-ttu-id="3b007-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b007-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b007-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3b007-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b007-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b007-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b007-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b007-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b007-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b007-116">See Also</span></span>  
 [<span data-ttu-id="3b007-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="3b007-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
