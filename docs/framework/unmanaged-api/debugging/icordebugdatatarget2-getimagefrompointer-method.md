---
title: "Método ICorDebugDataTarget2::GetImageFromPointer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e56f65aea12c71145c99a9a195b910ef2876aa09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="b7291-102">Método ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="b7291-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="b7291-103">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="b7291-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7291-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7291-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7291-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7291-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="b7291-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa una dirección de un módulo.</span><span class="sxs-lookup"><span data-stu-id="b7291-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="b7291-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="b7291-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="b7291-108">Puntero al tamaño del módulo.</span><span class="sxs-lookup"><span data-stu-id="b7291-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7291-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7291-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7291-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b7291-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7291-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7291-111">Requirements</span></span>  
 <span data-ttu-id="b7291-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7291-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7291-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7291-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7291-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7291-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7291-115">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7291-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7291-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7291-116">See Also</span></span>  
 [<span data-ttu-id="b7291-117">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="b7291-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="b7291-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b7291-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
