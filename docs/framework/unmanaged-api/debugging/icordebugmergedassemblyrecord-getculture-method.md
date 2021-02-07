---
description: 'Más información sobre: ICorDebugMergedAssemblyRecord:: getCulture ((método)'
title: ICorDebugMergedAssemblyRecord::GetCulture (método)
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: f530bb68a1e7e4c4bff53b8f3046f6ae9ca42aab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754009"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="9fba0-103">ICorDebugMergedAssemblyRecord::GetCulture (método)</span><span class="sxs-lookup"><span data-stu-id="9fba0-103">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>

<span data-ttu-id="9fba0-104">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9fba0-104">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fba0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fba0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fba0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fba0-106">Parameters</span></span>  

 `cchCulture`  
 <span data-ttu-id="9fba0-107">[in] Número de caracteres del búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="9fba0-107">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="9fba0-108">[out] Número de caracteres escritos realmente en el búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="9fba0-108">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="9fba0-109">[out] Matriz de caracteres que contiene el nombre de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="9fba0-109">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fba0-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9fba0-110">Remarks</span></span>  

 <span data-ttu-id="9fba0-111">El nombre de referencia cultural es una cadena única que identifica una referencia cultural, como "en-US" [para la referencia cultural inglés (Estados Unidos)] o "neutral" (para una referencia cultural neutra).</span><span class="sxs-lookup"><span data-stu-id="9fba0-111">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fba0-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9fba0-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fba0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fba0-113">Requirements</span></span>  

 <span data-ttu-id="9fba0-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fba0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fba0-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fba0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fba0-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fba0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fba0-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fba0-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fba0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fba0-118">See also</span></span>

- [<span data-ttu-id="9fba0-119">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="9fba0-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="9fba0-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9fba0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
