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
ms.openlocfilehash: 90304eb94e6f53d3132c97f5ababdc45f6053d7c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006576"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="d444e-102">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="d444e-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="d444e-103">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="d444e-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="d444e-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d444e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d444e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d444e-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d444e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d444e-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="d444e-107">de Identificador de una ventana en la que se mostrará el resultado del comando.</span><span class="sxs-lookup"><span data-stu-id="d444e-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="d444e-108">de Identificador de la biblioteca que contiene el comando.</span><span class="sxs-lookup"><span data-stu-id="d444e-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="d444e-109">de Cadena que especifica el comando que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d444e-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="d444e-110">de Un entero que especifica el modo de presentación de la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="d444e-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d444e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d444e-111">Requirements</span></span>  
 <span data-ttu-id="d444e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d444e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d444e-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d444e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d444e-114">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d444e-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d444e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d444e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d444e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d444e-116">See also</span></span>

- [<span data-ttu-id="d444e-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="d444e-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
