---
title: CreateAssemblyCache (Función)
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6327c9d7dee548957a569b587faefe3d6d9cb1b9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497774"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="7f630-102">CreateAssemblyCache (Función)</span><span class="sxs-lookup"><span data-stu-id="7f630-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="7f630-103">Obtiene un puntero a una nueva [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instancia que representa la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7f630-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f630-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f630-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f630-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7f630-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="7f630-106">[out] El valor devuelto `IAssemblyCache` puntero.</span><span class="sxs-lookup"><span data-stu-id="7f630-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="7f630-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="7f630-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7f630-108">`dwReserved` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="7f630-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f630-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f630-109">Requirements</span></span>  
 <span data-ttu-id="7f630-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f630-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f630-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7f630-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7f630-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f630-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f630-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f630-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f630-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f630-114">See also</span></span>
- [<span data-ttu-id="7f630-115">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f630-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="7f630-116">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="7f630-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="7f630-117">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="7f630-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
