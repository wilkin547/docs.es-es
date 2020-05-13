---
title: ICorDebugMergedAssemblyRecord::GetCulture (método)
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: f73aac169cc048a87aca3bfc325cf8c6243012e9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207867"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="bce03-102">ICorDebugMergedAssemblyRecord::GetCulture (método)</span><span class="sxs-lookup"><span data-stu-id="bce03-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="bce03-103">Obtiene la cadena de nombre de referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bce03-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce03-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bce03-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bce03-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bce03-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="bce03-106">[in] Número de caracteres del búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="bce03-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="bce03-107">[out] Número de caracteres escritos realmente en el búfer `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="bce03-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="bce03-108">[out] Matriz de caracteres que contiene el nombre de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="bce03-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bce03-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bce03-109">Remarks</span></span>  
 <span data-ttu-id="bce03-110">El nombre de referencia cultural es una cadena única que identifica una referencia cultural, como "en-US" [para la referencia cultural inglés (Estados Unidos)] o "neutral" (para una referencia cultural neutra).</span><span class="sxs-lookup"><span data-stu-id="bce03-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bce03-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bce03-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bce03-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bce03-112">Requirements</span></span>  
 <span data-ttu-id="bce03-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bce03-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bce03-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bce03-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bce03-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bce03-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bce03-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bce03-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce03-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bce03-117">See also</span></span>

- [<span data-ttu-id="bce03-118">Interfaz ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="bce03-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="bce03-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="bce03-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
