---
description: 'Más información acerca de: Rundll32shimw ((función)'
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
ms.openlocfilehash: d01021358a6cddf15d1a0e1b223c9acff3c64ff7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679503"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="ec330-103">RunDll32ShimW (Función)</span><span class="sxs-lookup"><span data-stu-id="ec330-103">RunDll32ShimW Function</span></span>

<span data-ttu-id="ec330-104">Ejecuta el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="ec330-104">Executes the specified command.</span></span>  
  
 <span data-ttu-id="ec330-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ec330-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec330-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec330-106">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec330-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec330-107">Parameters</span></span>  

 `hwnd`  
 <span data-ttu-id="ec330-108">de Identificador de una ventana en la que se mostrará el resultado del comando.</span><span class="sxs-lookup"><span data-stu-id="ec330-108">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="ec330-109">de Identificador de la biblioteca que contiene el comando.</span><span class="sxs-lookup"><span data-stu-id="ec330-109">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="ec330-110">de Cadena que especifica el comando que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="ec330-110">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="ec330-111">de Un entero que especifica el modo de presentación de la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="ec330-111">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec330-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec330-112">Requirements</span></span>  

 <span data-ttu-id="ec330-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec330-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec330-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ec330-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec330-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec330-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec330-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec330-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec330-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec330-117">See also</span></span>

- [<span data-ttu-id="ec330-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="ec330-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
