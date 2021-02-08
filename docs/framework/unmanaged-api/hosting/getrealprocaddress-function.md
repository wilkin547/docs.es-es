---
description: 'Más información acerca de: GetRealProcAddress ((función)'
title: GetRealProcAddress (Función)
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: b8b3db77d6aef7fae3045a7aa2310c1fadc70e91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785320"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="1e7bb-103">GetRealProcAddress (Función)</span><span class="sxs-lookup"><span data-stu-id="1e7bb-103">GetRealProcAddress Function</span></span>

<span data-ttu-id="1e7bb-104">Obtiene la dirección de la función especificada que se exporta de la última versión instalada del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1e7bb-104">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="1e7bb-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e7bb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e7bb-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e7bb-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e7bb-107">Parameters</span></span>  

 `pwszProcName`  
 <span data-ttu-id="1e7bb-108">de Nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-108">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="1e7bb-109">enuncia La ubicación que recibe un puntero a la dirección de la función.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-109">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e7bb-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1e7bb-110">Return Value</span></span>  

 <span data-ttu-id="1e7bb-111">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los siguientes valores definidos en CorError. h.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-111">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="1e7bb-112">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="1e7bb-112">Return code</span></span>|<span data-ttu-id="1e7bb-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e7bb-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1e7bb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e7bb-114">S_OK</span></span>|<span data-ttu-id="1e7bb-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="1e7bb-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1e7bb-116">E_POINTER</span></span>|<span data-ttu-id="1e7bb-117">`ppv` no es válido.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-117">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="1e7bb-118">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="1e7bb-118">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="1e7bb-119">La función no se exporta desde el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-119">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e7bb-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e7bb-120">Requirements</span></span>  

 <span data-ttu-id="1e7bb-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e7bb-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e7bb-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1e7bb-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e7bb-123">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e7bb-123">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e7bb-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e7bb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7bb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e7bb-125">See also</span></span>

- [<span data-ttu-id="1e7bb-126">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="1e7bb-126">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
