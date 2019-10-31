---
title: ICorDebugProcess5::GetTypeLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: a348c3b2ad33a5d68b1bc46e9a284f2d2a9c7304
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121283"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="89116-102">ICorDebugProcess5::GetTypeLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="89116-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="89116-103">Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="89116-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89116-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89116-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89116-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89116-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="89116-106">de Un token [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) que especifica el tipo cuyo diseño se desea.</span><span class="sxs-lookup"><span data-stu-id="89116-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="89116-107">enuncia Puntero a una estructura [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) que contiene información sobre el diseño del objeto en memoria.</span><span class="sxs-lookup"><span data-stu-id="89116-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89116-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89116-108">Remarks</span></span>  
 <span data-ttu-id="89116-109">El método `ICorDebugProcess5::GetTypeLayout` proporciona información sobre un objeto basado en su [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), que es devuelto por una serie de otros métodos [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="89116-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="89116-110">La información se proporciona mediante una estructura [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) que rellena el método.</span><span class="sxs-lookup"><span data-stu-id="89116-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89116-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89116-111">Requirements</span></span>  
 <span data-ttu-id="89116-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89116-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89116-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89116-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89116-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89116-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89116-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89116-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89116-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="89116-116">See also</span></span>

- [<span data-ttu-id="89116-117">COR_TYPE_LAYOUT (estructura)</span><span class="sxs-lookup"><span data-stu-id="89116-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [<span data-ttu-id="89116-118">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89116-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="89116-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="89116-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
