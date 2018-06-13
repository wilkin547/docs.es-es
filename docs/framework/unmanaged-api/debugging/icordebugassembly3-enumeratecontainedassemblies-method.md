---
title: Método ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb84efe78568bbae03f76efc456fc8ae605e4db9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404848"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="18454-102">Método ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="18454-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="18454-103">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="18454-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18454-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18454-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18454-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="18454-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="18454-106">[out] Un puntero a la dirección de un objeto de interfaz de ICorDebugAssemblyEnum que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="18454-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18454-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="18454-107">Return Value</span></span>  
 <span data-ttu-id="18454-108">`S_OK` si el objeto `ICorDebugAssembly3` es un contenedor; de lo contrario, `S_FALSE` y la enumeración está vacía.</span><span class="sxs-lookup"><span data-stu-id="18454-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18454-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18454-109">Remarks</span></span>  
 <span data-ttu-id="18454-110">Se necesitan símbolos para enumerar los ensamblados contenidos.</span><span class="sxs-lookup"><span data-stu-id="18454-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="18454-111">Si no existen, el método devuelve `S_FALSE` y no se proporciona un enumerador válido.</span><span class="sxs-lookup"><span data-stu-id="18454-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18454-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="18454-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18454-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18454-113">Requirements</span></span>  
 <span data-ttu-id="18454-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18454-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18454-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18454-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18454-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18454-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18454-117">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18454-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18454-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="18454-118">See Also</span></span>  
 [<span data-ttu-id="18454-119">ICorDebugAssembly3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="18454-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="18454-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="18454-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
