---
title: Método ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: e466a62761cc6dd1f1fc0a54f05d54f85c190d07
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724941"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="eaf19-102">Método ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="eaf19-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>

<span data-ttu-id="eaf19-103">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="eaf19-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf19-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eaf19-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaf19-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eaf19-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="eaf19-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="eaf19-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="eaf19-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="eaf19-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="eaf19-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="eaf19-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaf19-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eaf19-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eaf19-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="eaf19-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaf19-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eaf19-111">Requirements</span></span>  

 <span data-ttu-id="eaf19-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaf19-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf19-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eaf19-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eaf19-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaf19-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaf19-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf19-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf19-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eaf19-116">See also</span></span>

- [<span data-ttu-id="eaf19-117">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="eaf19-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="eaf19-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="eaf19-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
