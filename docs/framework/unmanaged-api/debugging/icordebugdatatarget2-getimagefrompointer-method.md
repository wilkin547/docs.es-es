---
title: Método ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 55c87731399cf1e7a6747720b8bb33de7e01906c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788843"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="bb334-102">Método ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="bb334-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="bb334-103">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="bb334-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb334-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb334-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb334-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="bb334-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="bb334-106">[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa una dirección de un módulo.</span><span class="sxs-lookup"><span data-stu-id="bb334-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="bb334-107">enuncia [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="bb334-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="bb334-108">Puntero al tamaño del módulo.</span><span class="sxs-lookup"><span data-stu-id="bb334-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb334-109">Notas</span><span class="sxs-lookup"><span data-stu-id="bb334-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb334-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bb334-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb334-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="bb334-111">Requirements</span></span>  
 <span data-ttu-id="bb334-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb334-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb334-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb334-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb334-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb334-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb334-115">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb334-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb334-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb334-116">See also</span></span>

- [<span data-ttu-id="bb334-117">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb334-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="bb334-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bb334-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
