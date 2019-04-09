---
title: Método ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080961"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="ac0e4-102">Método ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="ac0e4-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="ac0e4-103">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac0e4-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac0e4-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac0e4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac0e4-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="ac0e4-106">[out] Un puntero a la dirección de un objeto de interfaz ICorDebugAssemblyEnum que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="ac0e4-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac0e4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac0e4-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="ac0e4-108">Si este `ICorDebugAssembly3` objeto es un contenedor; de lo contrario, `S_FALSE`, y la enumeración está vacía.</span><span class="sxs-lookup"><span data-stu-id="ac0e4-108">if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac0e4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac0e4-109">Remarks</span></span>  
 <span data-ttu-id="ac0e4-110">Se necesitan símbolos para enumerar los ensamblados contenidos.</span><span class="sxs-lookup"><span data-stu-id="ac0e4-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="ac0e4-111">Si no existen, el método devuelve `S_FALSE` y no se proporciona un enumerador válido.</span><span class="sxs-lookup"><span data-stu-id="ac0e4-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac0e4-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ac0e4-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac0e4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac0e4-113">Requirements</span></span>  
 <span data-ttu-id="ac0e4-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac0e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac0e4-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac0e4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac0e4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac0e4-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ac0e4-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ac0e4-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ac0e4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac0e4-118">See also</span></span>

- [<span data-ttu-id="ac0e4-119">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="ac0e4-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="ac0e4-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ac0e4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
