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
ms.openlocfilehash: ffeb04ddcec290f899556bf0d8078acfb06707ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778608"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="a080f-102">CreateAssemblyCache (Función)</span><span class="sxs-lookup"><span data-stu-id="a080f-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="a080f-103">Obtiene un puntero a una nueva [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instancia que representa la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a080f-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a080f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a080f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a080f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a080f-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="a080f-106">[out] El valor devuelto `IAssemblyCache` puntero.</span><span class="sxs-lookup"><span data-stu-id="a080f-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="a080f-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="a080f-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a080f-108">`dwReserved` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="a080f-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a080f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a080f-109">Requirements</span></span>  
 <span data-ttu-id="a080f-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a080f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a080f-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a080f-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a080f-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a080f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a080f-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a080f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a080f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a080f-114">See also</span></span>

- [<span data-ttu-id="a080f-115">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a080f-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="a080f-116">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="a080f-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="a080f-117">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="a080f-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
