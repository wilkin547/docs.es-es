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
ms.openlocfilehash: e661bd82ecf6d804e852cca4a4478084edf303c5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141506"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="f15a2-102">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="f15a2-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="f15a2-103">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="f15a2-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="f15a2-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f15a2-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f15a2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f15a2-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f15a2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f15a2-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="f15a2-107">de Identificador de una ventana en la que se mostrará el resultado del comando.</span><span class="sxs-lookup"><span data-stu-id="f15a2-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="f15a2-108">de Identificador de la biblioteca que contiene el comando.</span><span class="sxs-lookup"><span data-stu-id="f15a2-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="f15a2-109">de Cadena que especifica el comando que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="f15a2-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="f15a2-110">de Un entero que especifica el modo de presentación de la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="f15a2-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f15a2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f15a2-111">Requirements</span></span>  
 <span data-ttu-id="f15a2-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f15a2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f15a2-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f15a2-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f15a2-114">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f15a2-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f15a2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f15a2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f15a2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f15a2-116">See also</span></span>

- [<span data-ttu-id="f15a2-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f15a2-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
