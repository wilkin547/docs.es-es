---
title: Método de ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 628f85f3045533ead7ace47b11573a0b1a46df46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782044"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="b23dd-102">Método de ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="b23dd-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="b23dd-103">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="b23dd-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b23dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b23dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b23dd-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b23dd-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b23dd-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="b23dd-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b23dd-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="b23dd-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="b23dd-108">[out] Matriz de caracteres que contiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="b23dd-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b23dd-109">Notas</span><span class="sxs-lookup"><span data-stu-id="b23dd-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b23dd-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b23dd-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b23dd-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b23dd-111">Requirements</span></span>  
 <span data-ttu-id="b23dd-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b23dd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b23dd-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b23dd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b23dd-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b23dd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b23dd-115">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b23dd-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b23dd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b23dd-116">See also</span></span>

- [<span data-ttu-id="b23dd-117">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b23dd-117">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="b23dd-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b23dd-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
