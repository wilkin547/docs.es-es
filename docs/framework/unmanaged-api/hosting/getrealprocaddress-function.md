---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0027514392dfbb93ab4189eb7c66a380fb77c1ae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778159"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="d90c6-102">GetRealProcAddress (Función)</span><span class="sxs-lookup"><span data-stu-id="d90c6-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="d90c6-103">Obtiene la dirección de la función especificada a la que se exporta desde la última versión instalada de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d90c6-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="d90c6-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d90c6-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d90c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d90c6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d90c6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d90c6-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="d90c6-107">[in] El nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="d90c6-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="d90c6-108">[out] La ubicación que recibe un puntero a la dirección de la función.</span><span class="sxs-lookup"><span data-stu-id="d90c6-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d90c6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d90c6-109">Return Value</span></span>  
 <span data-ttu-id="d90c6-110">Este método devuelve códigos de error de modelo de objetos componentes (COM) estándar, tal como se define en WinError.h, además de los siguientes valores definidos en CorError.h.</span><span class="sxs-lookup"><span data-stu-id="d90c6-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="d90c6-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="d90c6-111">Return code</span></span>|<span data-ttu-id="d90c6-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d90c6-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d90c6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d90c6-113">S_OK</span></span>|<span data-ttu-id="d90c6-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d90c6-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="d90c6-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d90c6-115">E_POINTER</span></span>|<span data-ttu-id="d90c6-116">`ppv` no es válido.</span><span class="sxs-lookup"><span data-stu-id="d90c6-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="d90c6-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="d90c6-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="d90c6-118">La función no se exporta desde el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d90c6-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d90c6-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d90c6-119">Requirements</span></span>  
 <span data-ttu-id="d90c6-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d90c6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d90c6-121">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d90c6-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d90c6-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d90c6-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d90c6-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d90c6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d90c6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d90c6-124">See also</span></span>

- [<span data-ttu-id="d90c6-125">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="d90c6-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
