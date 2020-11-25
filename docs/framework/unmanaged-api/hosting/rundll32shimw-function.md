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
ms.openlocfilehash: dd053134792b80a006849e465bc0025cf77a9ad8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729959"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="f74b8-102">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="f74b8-102">RunDll32ShimW Function</span></span>

<span data-ttu-id="f74b8-103">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="f74b8-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="f74b8-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f74b8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f74b8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f74b8-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f74b8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f74b8-106">Parameters</span></span>  

 `hwnd`  
 <span data-ttu-id="f74b8-107">de Identificador de una ventana en la que se mostrará el resultado del comando.</span><span class="sxs-lookup"><span data-stu-id="f74b8-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="f74b8-108">de Identificador de la biblioteca que contiene el comando.</span><span class="sxs-lookup"><span data-stu-id="f74b8-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="f74b8-109">de Cadena que especifica el comando que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="f74b8-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="f74b8-110">de Un entero que especifica el modo de presentación de la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="f74b8-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f74b8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f74b8-111">Requirements</span></span>  

 <span data-ttu-id="f74b8-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f74b8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f74b8-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f74b8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f74b8-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f74b8-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f74b8-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f74b8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f74b8-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f74b8-116">See also</span></span>

- [<span data-ttu-id="f74b8-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f74b8-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
