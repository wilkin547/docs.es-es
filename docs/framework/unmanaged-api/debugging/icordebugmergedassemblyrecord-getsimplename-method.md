---
title: ICorDebugMergedAssemblyRecord::GetSimpleNam (método)
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 11e43846f7b119933fb53bdf21423e28bbb792ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710550"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="ac9e3-102">ICorDebugMergedAssemblyRecord::GetSimpleNam (método)</span><span class="sxs-lookup"><span data-stu-id="ac9e3-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>

<span data-ttu-id="ac9e3-103">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac9e3-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac9e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac9e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac9e3-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="ac9e3-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="ac9e3-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ac9e3-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="ac9e3-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="ac9e3-108">Puntero a una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ac9e3-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac9e3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac9e3-109">Remarks</span></span>  

 <span data-ttu-id="ac9e3-110">Este método recupera el nombre sencillo de un ensamblado (por ejemplo, "System.Collections"), sin una extensión de archivo, versión, referencia cultural o el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="ac9e3-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="ac9e3-111">Se corresponde con la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> en código administrado.</span><span class="sxs-lookup"><span data-stu-id="ac9e3-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac9e3-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ac9e3-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9e3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac9e3-113">Requirements</span></span>  

 <span data-ttu-id="ac9e3-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac9e3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac9e3-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac9e3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac9e3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac9e3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac9e3-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9e3-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9e3-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac9e3-118">See also</span></span>

- [<span data-ttu-id="ac9e3-119">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="ac9e3-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="ac9e3-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ac9e3-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
