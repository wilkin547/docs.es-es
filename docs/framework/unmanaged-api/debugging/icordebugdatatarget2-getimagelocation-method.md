---
title: Método ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: 8b873e28bfab31ea18924f471f916475efd345d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122136"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="cd7c5-102">Método ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="cd7c5-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="cd7c5-103">Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="cd7c5-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd7c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd7c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd7c5-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="cd7c5-106">de Valor de [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="cd7c5-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="cd7c5-107">[in] Número de caracteres en el búfer que va a recibir la ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="cd7c5-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cd7c5-108">[out] Puntero al número de caracteres escritos en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="cd7c5-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="cd7c5-109">[out] Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="cd7c5-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd7c5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd7c5-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd7c5-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cd7c5-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd7c5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd7c5-112">Requirements</span></span>  
 <span data-ttu-id="cd7c5-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd7c5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd7c5-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd7c5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd7c5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd7c5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd7c5-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd7c5-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7c5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd7c5-117">See also</span></span>

- [<span data-ttu-id="cd7c5-118">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd7c5-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="cd7c5-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cd7c5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
