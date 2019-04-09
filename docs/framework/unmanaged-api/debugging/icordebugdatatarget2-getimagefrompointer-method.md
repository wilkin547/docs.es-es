---
title: Método ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dab9183075f563f52a4fc982eda5cb172556554
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154380"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="2a7a6-102">Método ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="2a7a6-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="2a7a6-103">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="2a7a6-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a7a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a7a6-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a7a6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a7a6-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="2a7a6-106">Un [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa una dirección de un módulo.</span><span class="sxs-lookup"><span data-stu-id="2a7a6-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="2a7a6-107">[out] Un [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="2a7a6-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="2a7a6-108">Puntero al tamaño del módulo.</span><span class="sxs-lookup"><span data-stu-id="2a7a6-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a7a6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a7a6-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a7a6-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2a7a6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a7a6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a7a6-111">Requirements</span></span>  
 <span data-ttu-id="2a7a6-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a7a6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a7a6-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a7a6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a7a6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a7a6-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2a7a6-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2a7a6-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2a7a6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a7a6-116">See also</span></span>

- [<span data-ttu-id="2a7a6-117">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="2a7a6-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="2a7a6-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2a7a6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
