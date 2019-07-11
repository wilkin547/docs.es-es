---
title: Método ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05c4e2a5c16f11f80cc8356a65b746eab81a3899
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744400"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="07173-102">Método ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="07173-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="07173-103">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="07173-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07173-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07173-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07173-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07173-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="07173-106">[out] Un puntero a la dirección de un objeto de interfaz ICorDebugAssemblyEnum que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="07173-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07173-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="07173-107">Return Value</span></span>  
 <span data-ttu-id="07173-108">`S_OK` si el objeto `ICorDebugAssembly3` es un contenedor; de lo contrario, `S_FALSE` y la enumeración está vacía.</span><span class="sxs-lookup"><span data-stu-id="07173-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07173-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07173-109">Remarks</span></span>  
 <span data-ttu-id="07173-110">Se necesitan símbolos para enumerar los ensamblados contenidos.</span><span class="sxs-lookup"><span data-stu-id="07173-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="07173-111">Si no existen, el método devuelve `S_FALSE` y no se proporciona un enumerador válido.</span><span class="sxs-lookup"><span data-stu-id="07173-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07173-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="07173-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07173-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07173-113">Requirements</span></span>  
 <span data-ttu-id="07173-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07173-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07173-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07173-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07173-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07173-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07173-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07173-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07173-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="07173-118">See also</span></span>

- [<span data-ttu-id="07173-119">ICorDebugAssembly3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="07173-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="07173-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="07173-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
