---
title: 'ICorDebugMergedAssemblyRecord:: GetSimpleName (método)'
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 565e27b47f2454dec1e4c2b89ee46ac5279b08b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130552"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="7b815-102">ICorDebugMergedAssemblyRecord:: GetSimpleName (método)</span><span class="sxs-lookup"><span data-stu-id="7b815-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="7b815-103">Obtiene el nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7b815-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b815-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b815-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b815-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b815-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="7b815-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="7b815-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7b815-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="7b815-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="7b815-108">Puntero a una matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7b815-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b815-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b815-109">Remarks</span></span>  
 <span data-ttu-id="7b815-110">Este método recupera el nombre sencillo de un ensamblado (por ejemplo, "System.Collections"), sin una extensión de archivo, versión, referencia cultural o el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="7b815-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="7b815-111">Se corresponde con la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> en código administrado.</span><span class="sxs-lookup"><span data-stu-id="7b815-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b815-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7b815-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b815-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b815-113">Requirements</span></span>  
 <span data-ttu-id="7b815-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b815-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b815-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b815-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b815-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b815-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b815-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b815-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b815-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b815-118">See also</span></span>

- [<span data-ttu-id="7b815-119">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b815-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="7b815-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7b815-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
