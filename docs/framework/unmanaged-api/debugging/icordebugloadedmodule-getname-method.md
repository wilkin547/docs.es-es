---
title: Método de ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e97c7c793df389dd6a8f670e985a9c9384eab639
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703749"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="8edea-102">Método de ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="8edea-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="8edea-103">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="8edea-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8edea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8edea-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8edea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8edea-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8edea-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="8edea-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8edea-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="8edea-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="8edea-108">[out] Matriz de caracteres que contiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="8edea-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8edea-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8edea-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8edea-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8edea-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8edea-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8edea-111">Requirements</span></span>  
 <span data-ttu-id="8edea-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8edea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8edea-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8edea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8edea-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8edea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8edea-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8edea-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8edea-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8edea-116">See also</span></span>
- [<span data-ttu-id="8edea-117">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8edea-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="8edea-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8edea-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
