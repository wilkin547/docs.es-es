---
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: d8c91c10577efd6a76af778cd01002de006df43a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209882"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="61b59-102">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="61b59-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="61b59-103">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="61b59-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61b59-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61b59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61b59-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="61b59-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="61b59-106">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="61b59-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61b59-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="61b59-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61b59-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="61b59-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61b59-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61b59-109">Requirements</span></span>  
 <span data-ttu-id="61b59-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61b59-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61b59-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61b59-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61b59-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61b59-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61b59-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61b59-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b59-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61b59-114">See also</span></span>

- [<span data-ttu-id="61b59-115">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="61b59-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="61b59-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="61b59-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
