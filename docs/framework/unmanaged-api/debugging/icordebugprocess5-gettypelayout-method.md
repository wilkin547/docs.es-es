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
ms.openlocfilehash: 306d881c05c2fcdb15a53a439bfce6eff3afffa8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792309"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="4d42e-102">ICorDebugProcess5::GetTypeLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="4d42e-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="4d42e-103">Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="4d42e-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d42e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d42e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d42e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4d42e-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="4d42e-106">de [COR_TYPEID](cor-typeid-structure.md) token que especifica el tipo cuyo diseño se desea.</span><span class="sxs-lookup"><span data-stu-id="4d42e-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="4d42e-107">enuncia Puntero a una estructura de [COR_TYPE_LAYOUT](cor-type-layout-structure.md) que contiene información sobre el diseño del objeto en memoria.</span><span class="sxs-lookup"><span data-stu-id="4d42e-107">[out] A pointer to a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d42e-108">Notas</span><span class="sxs-lookup"><span data-stu-id="4d42e-108">Remarks</span></span>  
 <span data-ttu-id="4d42e-109">El método `ICorDebugProcess5::GetTypeLayout` proporciona información sobre un objeto basándose en su [COR_TYPEID](cor-typeid-structure.md), que es devuelto por una serie de otros métodos [ICorDebugProcess5](icordebugprocess5-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4d42e-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="4d42e-110">La información se proporciona mediante una estructura de [COR_TYPE_LAYOUT](cor-type-layout-structure.md) rellenada por el método.</span><span class="sxs-lookup"><span data-stu-id="4d42e-110">The information is provided by a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d42e-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4d42e-111">Requirements</span></span>  
 <span data-ttu-id="4d42e-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d42e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d42e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d42e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d42e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d42e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d42e-115">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d42e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d42e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d42e-116">See also</span></span>

- [<span data-ttu-id="4d42e-117">COR_TYPE_LAYOUT (estructura)</span><span class="sxs-lookup"><span data-stu-id="4d42e-117">COR_TYPE_LAYOUT Structure</span></span>](cor-type-layout-structure.md)
- [<span data-ttu-id="4d42e-118">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d42e-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="4d42e-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4d42e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
