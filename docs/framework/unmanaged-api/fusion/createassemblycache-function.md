---
description: 'Más información acerca de: Createassemblycache ((función)'
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
ms.openlocfilehash: 1646e1d33401c557b13ae5c025f53aef48042004
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761166"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="3506c-103">CreateAssemblyCache (Función)</span><span class="sxs-lookup"><span data-stu-id="3506c-103">CreateAssemblyCache Function</span></span>

<span data-ttu-id="3506c-104">Obtiene un puntero a una nueva instancia de [IAssemblyCache](iassemblycache-interface.md) que representa la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3506c-104">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3506c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3506c-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3506c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3506c-106">Parameters</span></span>  

 `ppAsmCache`  
 <span data-ttu-id="3506c-107">enuncia Puntero devuelto `IAssemblyCache` .</span><span class="sxs-lookup"><span data-stu-id="3506c-107">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="3506c-108">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="3506c-108">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3506c-109">`dwReserved` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="3506c-109">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3506c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3506c-110">Requirements</span></span>  

 <span data-ttu-id="3506c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3506c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3506c-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3506c-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3506c-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3506c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3506c-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3506c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3506c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3506c-115">See also</span></span>

- [<span data-ttu-id="3506c-116">IAssemblyCache (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3506c-116">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="3506c-117">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="3506c-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="3506c-118">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3506c-118">Global Assembly Cache</span></span>](../../app-domains/gac.md)
