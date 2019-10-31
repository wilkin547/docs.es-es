---
title: Método de ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 4cf2c5c099de3d66878f09ff702a1cad6ddb8f57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122624"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="9e3de-102">Método de ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="9e3de-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="9e3de-103">Obtiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="9e3de-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e3de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e3de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e3de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e3de-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9e3de-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9e3de-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9e3de-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9e3de-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="9e3de-108">[out] Matriz de caracteres que contiene el nombre del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="9e3de-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e3de-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e3de-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e3de-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9e3de-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e3de-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e3de-111">Requirements</span></span>  
 <span data-ttu-id="9e3de-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e3de-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e3de-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e3de-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e3de-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e3de-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e3de-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e3de-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e3de-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e3de-116">See also</span></span>

- [<span data-ttu-id="9e3de-117">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e3de-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="9e3de-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9e3de-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
