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
ms.openlocfilehash: 5ef100680328e9ad6261bb9188d7509efa9ab479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108865"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="4a34a-102">CreateAssemblyCache (Función)</span><span class="sxs-lookup"><span data-stu-id="4a34a-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="4a34a-103">Obtiene un puntero a una nueva instancia de [IAssemblyCache](iassemblycache-interface.md) que representa la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4a34a-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a34a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a34a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a34a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a34a-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="4a34a-106">enuncia Puntero `IAssemblyCache` devuelto.</span><span class="sxs-lookup"><span data-stu-id="4a34a-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="4a34a-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4a34a-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4a34a-108">`dwReserved` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="4a34a-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a34a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a34a-109">Requirements</span></span>  
 <span data-ttu-id="4a34a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a34a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a34a-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4a34a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4a34a-112">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a34a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a34a-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a34a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a34a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a34a-114">See also</span></span>

- [<span data-ttu-id="4a34a-115">IAssemblyCache (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a34a-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="4a34a-116">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="4a34a-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="4a34a-117">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="4a34a-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
