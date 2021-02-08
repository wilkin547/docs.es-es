---
description: 'Más información acerca de: ICorDebugInstanceFieldSymbol:: GetName (método)'
title: Método ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: 9cc2106d1527aa0b4d9e5c52115b703ffe55037f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791197"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="39b10-103">Método ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="39b10-103">ICorDebugInstanceFieldSymbol::GetName Method</span></span>

<span data-ttu-id="39b10-104">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="39b10-104">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b10-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39b10-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39b10-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39b10-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="39b10-107">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="39b10-107">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="39b10-108">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="39b10-108">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="39b10-109">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="39b10-109">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39b10-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39b10-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39b10-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="39b10-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39b10-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39b10-112">Requirements</span></span>  

 <span data-ttu-id="39b10-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39b10-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39b10-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39b10-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39b10-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39b10-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39b10-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39b10-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b10-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="39b10-117">See also</span></span>

- [<span data-ttu-id="39b10-118">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="39b10-118">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="39b10-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="39b10-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
