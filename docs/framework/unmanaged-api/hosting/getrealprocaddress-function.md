---
title: "GetRealProcAddress (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ade1c902d00e991612406041ef0a0b2c1bb884e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="b6882-102">GetRealProcAddress (Función)</span><span class="sxs-lookup"><span data-stu-id="b6882-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="b6882-103">Obtiene la dirección de la función especificada que se exporta desde la última versión instalada de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b6882-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="b6882-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6882-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6882-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6882-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6882-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6882-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="b6882-107">[in] El nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="b6882-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="b6882-108">[out] La ubicación que recibe un puntero a la dirección de la función.</span><span class="sxs-lookup"><span data-stu-id="b6882-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6882-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6882-109">Return Value</span></span>  
 <span data-ttu-id="b6882-110">Este método devuelve códigos de error estándar de modelo de objetos componentes (COM), como se define en WinError.h, además de los siguientes valores definidos en CorError.h.</span><span class="sxs-lookup"><span data-stu-id="b6882-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="b6882-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="b6882-111">Return code</span></span>|<span data-ttu-id="b6882-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6882-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b6882-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6882-113">S_OK</span></span>|<span data-ttu-id="b6882-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6882-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b6882-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b6882-115">E_POINTER</span></span>|<span data-ttu-id="b6882-116">`ppv` no es válido.</span><span class="sxs-lookup"><span data-stu-id="b6882-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="b6882-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="b6882-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="b6882-118">La función no se exporta desde el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6882-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6882-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6882-119">Requirements</span></span>  
 <span data-ttu-id="b6882-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6882-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6882-121">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b6882-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6882-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6882-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6882-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6882-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6882-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6882-124">See Also</span></span>  
 [<span data-ttu-id="b6882-125">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="b6882-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
