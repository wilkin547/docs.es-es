---
title: ICorDebugMergedAssemblyRecord::GetCulture (método)
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: 636d0fd25d345f513e00504b9eb5adb4f0c03b0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710654"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="cc6dc-102">ICorDebugMergedAssemblyRecord::GetCulture (método)</span><span class="sxs-lookup"><span data-stu-id="cc6dc-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>

<span data-ttu-id="cc6dc-103">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cc6dc-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc6dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc6dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc6dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc6dc-105">Parameters</span></span>  

 `cchCulture`  
 <span data-ttu-id="cc6dc-106">[in] Número de caracteres del búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="cc6dc-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="cc6dc-107">[out] Número de caracteres escritos realmente en el búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="cc6dc-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="cc6dc-108">[out] Matriz de caracteres que contiene el nombre de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="cc6dc-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc6dc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc6dc-109">Remarks</span></span>  

 <span data-ttu-id="cc6dc-110">El nombre de referencia cultural es una cadena única que identifica una referencia cultural, como "en-US" [para la referencia cultural inglés (Estados Unidos)] o "neutral" (para una referencia cultural neutra).</span><span class="sxs-lookup"><span data-stu-id="cc6dc-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc6dc-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cc6dc-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc6dc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc6dc-112">Requirements</span></span>  

 <span data-ttu-id="cc6dc-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc6dc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc6dc-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc6dc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc6dc-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc6dc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc6dc-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc6dc-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc6dc-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc6dc-117">See also</span></span>

- [<span data-ttu-id="cc6dc-118">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="cc6dc-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="cc6dc-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cc6dc-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
