---
description: 'Más información acerca de: Callfunctionshim ((función)'
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
ms.openlocfilehash: 7ddd16a06005011adcf41190929fd62f4132f14d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799959"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="7582d-103">CallFunctionShim (Función)</span><span class="sxs-lookup"><span data-stu-id="7582d-103">CallFunctionShim Function</span></span>

<span data-ttu-id="7582d-104">Realiza una llamada a la función que tiene el nombre y los parámetros especificados en la biblioteca especificada.</span><span class="sxs-lookup"><span data-stu-id="7582d-104">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="7582d-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7582d-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7582d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7582d-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7582d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7582d-107">Parameters</span></span>  

 `szDllName`  
 <span data-ttu-id="7582d-108">de Nombre de la biblioteca que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="7582d-108">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="7582d-109">de Nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="7582d-109">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="7582d-110">de Primer argumento que se va a pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="7582d-110">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="7582d-111">de Segundo argumento que se va a pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="7582d-111">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="7582d-112">de Versión de la biblioteca que contiene la función.</span><span class="sxs-lookup"><span data-stu-id="7582d-112">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7582d-113">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="7582d-113">[in] Reserved for future use.</span></span> <span data-ttu-id="7582d-114">Pase cero en este parámetro.</span><span class="sxs-lookup"><span data-stu-id="7582d-114">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7582d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7582d-115">Requirements</span></span>  

 <span data-ttu-id="7582d-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7582d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7582d-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7582d-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7582d-118">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7582d-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7582d-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7582d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7582d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7582d-120">See also</span></span>

- [<span data-ttu-id="7582d-121">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="7582d-121">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
