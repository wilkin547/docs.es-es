---
title: Método ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e382dbadc3acf6ca4bc7cad2ca37d58125a82be2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488544"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="f517f-102">Método ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="f517f-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="f517f-103">Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="f517f-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f517f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f517f-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f517f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f517f-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="f517f-106">[in] Un [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="f517f-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f517f-107">[in] Número de caracteres en el búfer que va a recibir la ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="f517f-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f517f-108">[out] Puntero al número de caracteres escritos en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="f517f-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="f517f-109">[out] Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="f517f-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f517f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f517f-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f517f-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f517f-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f517f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f517f-112">Requirements</span></span>  
 <span data-ttu-id="f517f-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f517f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f517f-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f517f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f517f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f517f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f517f-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f517f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f517f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f517f-117">See also</span></span>
- [<span data-ttu-id="f517f-118">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f517f-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="f517f-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f517f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
