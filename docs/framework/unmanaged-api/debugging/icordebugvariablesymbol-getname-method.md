---
title: ICorDebugVariableSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f514acbd772c9d33ec4372cfaccb778d6bb41eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170175"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="3cebb-102">ICorDebugVariableSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="3cebb-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="3cebb-103">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="3cebb-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cebb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cebb-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cebb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cebb-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3cebb-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="3cebb-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3cebb-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="3cebb-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="3cebb-108">Puntero a una matriz de caracteres que contiene el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="3cebb-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cebb-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3cebb-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cebb-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3cebb-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cebb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cebb-111">Requirements</span></span>  
 <span data-ttu-id="3cebb-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cebb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cebb-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cebb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cebb-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cebb-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3cebb-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3cebb-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cebb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cebb-116">See also</span></span>

- [<span data-ttu-id="3cebb-117">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="3cebb-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="3cebb-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3cebb-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
