---
title: 'ICorDebugMergedAssemblyRecord:: getCulture ((método)'
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: f39a1f17c80d27a38c0f2a8a516405f72c79bbcf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131423"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="e1c5e-102">ICorDebugMergedAssemblyRecord:: getCulture ((método)</span><span class="sxs-lookup"><span data-stu-id="e1c5e-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="e1c5e-103">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e1c5e-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c5e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1c5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1c5e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1c5e-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="e1c5e-106">[in] Número de caracteres del búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="e1c5e-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="e1c5e-107">[out] Número de caracteres escritos realmente en el búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="e1c5e-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="e1c5e-108">[out] Matriz de caracteres que contiene el nombre de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="e1c5e-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1c5e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1c5e-109">Remarks</span></span>  
 <span data-ttu-id="e1c5e-110">El nombre de referencia cultural es una cadena única que identifica una referencia cultural, como "en-US" [para la referencia cultural inglés (Estados Unidos)] o "neutral" (para una referencia cultural neutra).</span><span class="sxs-lookup"><span data-stu-id="e1c5e-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1c5e-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e1c5e-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1c5e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1c5e-112">Requirements</span></span>  
 <span data-ttu-id="e1c5e-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1c5e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1c5e-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1c5e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1c5e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1c5e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1c5e-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1c5e-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c5e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1c5e-117">See also</span></span>

- [<span data-ttu-id="e1c5e-118">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1c5e-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="e1c5e-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e1c5e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
