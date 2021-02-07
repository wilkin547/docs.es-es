---
description: 'Más información sobre: ICorDebugProcess5:: Gettypelayout ((método)'
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
ms.openlocfilehash: d4496fa832b048dfc0bbe792aeb8fdcd460f5158
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746287"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="0da00-103">ICorDebugProcess5::GetTypeLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="0da00-103">ICorDebugProcess5::GetTypeLayout Method</span></span>

<span data-ttu-id="0da00-104">Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="0da00-104">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da00-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0da00-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da00-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0da00-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="0da00-107">de [COR_TYPEID](cor-typeid-structure.md) token que especifica el tipo cuyo diseño se desea.</span><span class="sxs-lookup"><span data-stu-id="0da00-107">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="0da00-108">enuncia Puntero a una estructura de [COR_TYPE_LAYOUT](cor-type-layout-structure.md) que contiene información sobre el diseño del objeto en memoria.</span><span class="sxs-lookup"><span data-stu-id="0da00-108">[out] A pointer to a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0da00-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0da00-109">Remarks</span></span>  

 <span data-ttu-id="0da00-110">El `ICorDebugProcess5::GetTypeLayout` método proporciona información sobre un objeto basándose en su [COR_TYPEID](cor-typeid-structure.md), que es devuelto por una serie de otros métodos [ICorDebugProcess5](icordebugprocess5-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0da00-110">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="0da00-111">La información se proporciona mediante una estructura de [COR_TYPE_LAYOUT](cor-type-layout-structure.md) rellenada por el método.</span><span class="sxs-lookup"><span data-stu-id="0da00-111">The information is provided by a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da00-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0da00-112">Requirements</span></span>  

 <span data-ttu-id="0da00-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0da00-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da00-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0da00-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0da00-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0da00-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0da00-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da00-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da00-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0da00-117">See also</span></span>

- [<span data-ttu-id="0da00-118">COR_TYPE_LAYOUT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0da00-118">COR_TYPE_LAYOUT Structure</span></span>](cor-type-layout-structure.md)
- [<span data-ttu-id="0da00-119">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0da00-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="0da00-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0da00-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
