---
description: 'Más información acerca de: ICorDebugStaticFieldSymbol:: GetName (método)'
title: ICorDebugStaticFieldSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: c74de604f5880a69b77c89e56a82ae08517dd69c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794707"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="53670-103">ICorDebugStaticFieldSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="53670-103">ICorDebugStaticFieldSymbol::GetName Method</span></span>

<span data-ttu-id="53670-104">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="53670-104">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53670-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53670-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53670-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53670-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="53670-107">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="53670-107">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="53670-108">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="53670-108">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="53670-109">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="53670-109">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53670-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="53670-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53670-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="53670-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53670-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53670-112">Requirements</span></span>  

 <span data-ttu-id="53670-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53670-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53670-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53670-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53670-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53670-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53670-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53670-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53670-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="53670-117">See also</span></span>

- [<span data-ttu-id="53670-118">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="53670-118">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="53670-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="53670-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
