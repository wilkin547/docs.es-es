---
description: 'Más información sobre: ICorDebugLoadedModule:: GetBaseAddress ((método)'
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 2852131d543cfb9593cf4ff607d1f752226c2880
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801272"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="cf65b-103">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="cf65b-103">ICorDebugLoadedModule::GetBaseAddress Method</span></span>

<span data-ttu-id="cf65b-104">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="cf65b-104">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf65b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf65b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf65b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf65b-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="cf65b-107">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="cf65b-107">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf65b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf65b-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf65b-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cf65b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf65b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf65b-110">Requirements</span></span>  

 <span data-ttu-id="cf65b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf65b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf65b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf65b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf65b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf65b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf65b-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf65b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf65b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf65b-115">See also</span></span>

- [<span data-ttu-id="cf65b-116">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="cf65b-116">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="cf65b-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cf65b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
