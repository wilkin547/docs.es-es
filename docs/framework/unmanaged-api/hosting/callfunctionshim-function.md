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
ms.openlocfilehash: e8945d40a3761ec51a73a8ae90ddc1d84ccab651
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616871"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="9566c-102">CallFunctionShim (Función)</span><span class="sxs-lookup"><span data-stu-id="9566c-102">CallFunctionShim Function</span></span>
<span data-ttu-id="9566c-103">Realiza una llamada a la función que tiene el nombre y los parámetros especificados en la biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="9566c-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="9566c-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9566c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9566c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9566c-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9566c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9566c-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="9566c-107">de Nombre de la biblioteca que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="9566c-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="9566c-108">de Nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="9566c-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="9566c-109">de Primer argumento que se va a pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="9566c-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="9566c-110">de Segundo argumento que se va a pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="9566c-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="9566c-111">de Versión de la biblioteca que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="9566c-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="9566c-112">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="9566c-112">[in] Reserved for future use.</span></span> <span data-ttu-id="9566c-113">Pase cero en este parámetro.</span><span class="sxs-lookup"><span data-stu-id="9566c-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9566c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9566c-114">Requirements</span></span>  
 <span data-ttu-id="9566c-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9566c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9566c-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9566c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9566c-117">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9566c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9566c-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9566c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9566c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9566c-119">See also</span></span>

- [<span data-ttu-id="9566c-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9566c-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
