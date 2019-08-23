---
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85748106edb34b98f975a40bcc2617401536e271
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910096"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="795de-102">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="795de-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="795de-103">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="795de-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="795de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="795de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="795de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="795de-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="795de-106">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="795de-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="795de-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="795de-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="795de-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="795de-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="795de-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="795de-109">Requirements</span></span>  
 <span data-ttu-id="795de-110">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="795de-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="795de-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="795de-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="795de-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="795de-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="795de-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="795de-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="795de-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="795de-114">See also</span></span>

- [<span data-ttu-id="795de-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="795de-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="795de-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="795de-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
