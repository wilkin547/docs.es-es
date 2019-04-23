---
title: Getculture (método)
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 093b21a439b96c9fe2f971300f314d1b75527f1f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207206"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="2ae78-102">Getculture (método)</span><span class="sxs-lookup"><span data-stu-id="2ae78-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="2ae78-103">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ae78-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae78-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ae78-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ae78-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ae78-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="2ae78-106">[in] Número de caracteres del búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="2ae78-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="2ae78-107">[out] Número de caracteres escritos realmente en el búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="2ae78-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="2ae78-108">[out] Matriz de caracteres que contiene el nombre de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="2ae78-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ae78-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ae78-109">Remarks</span></span>  
 <span data-ttu-id="2ae78-110">El nombre de referencia cultural es una cadena única que identifica una referencia cultural, como "en-US" [para la referencia cultural inglés (Estados Unidos)] o "neutral" (para una referencia cultural neutra).</span><span class="sxs-lookup"><span data-stu-id="2ae78-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ae78-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2ae78-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ae78-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ae78-112">Requirements</span></span>  
 <span data-ttu-id="2ae78-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ae78-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ae78-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ae78-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ae78-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ae78-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ae78-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ae78-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae78-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ae78-117">See also</span></span>

- [<span data-ttu-id="2ae78-118">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ae78-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="2ae78-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2ae78-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
