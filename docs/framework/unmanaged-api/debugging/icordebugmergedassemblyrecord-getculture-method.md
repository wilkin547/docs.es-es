---
title: ICorDebugMergedAssemblyRecord::GetCulture (método)
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f2336c89a32b202c4226f1ed194d786be6fa020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415362"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="1fc73-102">ICorDebugMergedAssemblyRecord::GetCulture (método)</span><span class="sxs-lookup"><span data-stu-id="1fc73-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="1fc73-103">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1fc73-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fc73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fc73-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1fc73-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1fc73-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="1fc73-106">[in] Número de caracteres del búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="1fc73-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="1fc73-107">[out] Número de caracteres escritos realmente en el búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="1fc73-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="1fc73-108">[out] Matriz de caracteres que contiene el nombre de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="1fc73-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fc73-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1fc73-109">Remarks</span></span>  
 <span data-ttu-id="1fc73-110">El nombre de referencia cultural es una cadena única que identifica una referencia cultural, como "en-US" [para la referencia cultural inglés (Estados Unidos)] o "neutral" (para una referencia cultural neutra).</span><span class="sxs-lookup"><span data-stu-id="1fc73-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1fc73-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1fc73-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fc73-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fc73-112">Requirements</span></span>  
 <span data-ttu-id="1fc73-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fc73-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fc73-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fc73-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fc73-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fc73-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fc73-116">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fc73-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc73-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fc73-117">See Also</span></span>  
 [<span data-ttu-id="1fc73-118">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1fc73-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="1fc73-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1fc73-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
