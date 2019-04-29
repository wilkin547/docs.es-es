---
title: Método ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dab9183075f563f52a4fc982eda5cb172556554
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782985"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="dfc76-102">Método ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="dfc76-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="dfc76-103">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="dfc76-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc76-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfc76-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfc76-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dfc76-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="dfc76-106">Un [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa una dirección de un módulo.</span><span class="sxs-lookup"><span data-stu-id="dfc76-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="dfc76-107">[out] Un [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="dfc76-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="dfc76-108">Puntero al tamaño del módulo.</span><span class="sxs-lookup"><span data-stu-id="dfc76-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfc76-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfc76-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfc76-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="dfc76-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfc76-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfc76-111">Requirements</span></span>  
 <span data-ttu-id="dfc76-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfc76-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfc76-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfc76-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfc76-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfc76-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfc76-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfc76-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc76-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfc76-116">See also</span></span>

- [<span data-ttu-id="dfc76-117">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfc76-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="dfc76-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dfc76-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
