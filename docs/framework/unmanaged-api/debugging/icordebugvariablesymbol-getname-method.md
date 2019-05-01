---
title: ICorDebugVariableSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f514acbd772c9d33ec4372cfaccb778d6bb41eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993634"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="165ec-102">ICorDebugVariableSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="165ec-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="165ec-103">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="165ec-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="165ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="165ec-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="165ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="165ec-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="165ec-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="165ec-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="165ec-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="165ec-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="165ec-108">Puntero a una matriz de caracteres que contiene el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="165ec-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="165ec-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="165ec-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="165ec-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="165ec-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="165ec-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="165ec-111">Requirements</span></span>  
 <span data-ttu-id="165ec-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="165ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="165ec-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="165ec-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="165ec-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="165ec-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="165ec-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="165ec-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="165ec-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="165ec-116">See also</span></span>

- [<span data-ttu-id="165ec-117">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="165ec-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="165ec-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="165ec-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
