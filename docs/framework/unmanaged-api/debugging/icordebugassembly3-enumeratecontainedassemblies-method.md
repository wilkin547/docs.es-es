---
title: Método ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: aebf499d7d25caef80782cc5661a57048dc5f6a9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894860"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="0393d-102">Método ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="0393d-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="0393d-103">Obtiene un enumerador para los ensamblados contenidos en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0393d-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0393d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0393d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0393d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0393d-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="0393d-106">[out] Puntero a la dirección de un objeto de interfaz ICorDebugAssemblyEnum que es el enumerador.</span><span class="sxs-lookup"><span data-stu-id="0393d-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0393d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0393d-107">Return Value</span></span>  
 <span data-ttu-id="0393d-108">`S_OK` si el objeto `ICorDebugAssembly3` es un contenedor; de lo contrario, `S_FALSE` y la enumeración está vacía.</span><span class="sxs-lookup"><span data-stu-id="0393d-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0393d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0393d-109">Remarks</span></span>  
 <span data-ttu-id="0393d-110">Se necesitan símbolos para enumerar los ensamblados contenidos.</span><span class="sxs-lookup"><span data-stu-id="0393d-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="0393d-111">Si no existen, el método devuelve `S_FALSE` y no se proporciona un enumerador válido.</span><span class="sxs-lookup"><span data-stu-id="0393d-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0393d-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0393d-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0393d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0393d-113">Requirements</span></span>  
 <span data-ttu-id="0393d-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0393d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0393d-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0393d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0393d-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0393d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0393d-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0393d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0393d-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0393d-118">See also</span></span>

- [<span data-ttu-id="0393d-119">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="0393d-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="0393d-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0393d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
