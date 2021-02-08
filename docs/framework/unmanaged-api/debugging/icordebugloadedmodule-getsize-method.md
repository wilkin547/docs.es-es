---
description: 'Más información acerca de: ICorDebugLoadedModule:: método de método'
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 6701d2578559a039f352df19bf9e859658c6687f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801246"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="5f449-103">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="5f449-103">ICorDebugLoadedModule::GetSize Method</span></span>

<span data-ttu-id="5f449-104">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="5f449-104">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f449-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f449-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f449-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f449-106">Parameters</span></span>  

 `pcBytes`  
 <span data-ttu-id="5f449-107">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="5f449-107">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f449-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5f449-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f449-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5f449-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f449-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f449-110">Requirements</span></span>  

 <span data-ttu-id="5f449-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f449-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f449-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f449-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f449-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f449-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f449-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f449-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f449-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f449-115">See also</span></span>

- [<span data-ttu-id="5f449-116">Interfaz de ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="5f449-116">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="5f449-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5f449-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
