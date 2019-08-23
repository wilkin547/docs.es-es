---
title: 'ICorDebugMergedAssemblyRecord:: getCulture ((método)'
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0f3ecee5a003587771871a178356d6dbfd8a636
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936842"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="9b7cf-102">ICorDebugMergedAssemblyRecord:: getCulture ((método)</span><span class="sxs-lookup"><span data-stu-id="9b7cf-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="9b7cf-103">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9b7cf-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b7cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b7cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b7cf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b7cf-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="9b7cf-106">[in] Número de caracteres del búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="9b7cf-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="9b7cf-107">[out] Número de caracteres escritos realmente en el búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="9b7cf-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="9b7cf-108">[out] Matriz de caracteres que contiene el nombre de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="9b7cf-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b7cf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9b7cf-109">Remarks</span></span>  
 <span data-ttu-id="9b7cf-110">El nombre de referencia cultural es una cadena única que identifica una referencia cultural, como "en-US" [para la referencia cultural inglés (Estados Unidos)] o "neutral" (para una referencia cultural neutra).</span><span class="sxs-lookup"><span data-stu-id="9b7cf-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b7cf-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9b7cf-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b7cf-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b7cf-112">Requirements</span></span>  
 <span data-ttu-id="9b7cf-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b7cf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b7cf-114">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="9b7cf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b7cf-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b7cf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b7cf-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b7cf-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7cf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b7cf-117">See also</span></span>

- [<span data-ttu-id="9b7cf-118">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b7cf-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="9b7cf-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9b7cf-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
