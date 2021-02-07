---
description: 'Más información acerca de: ICorDebugProcess5:: GetObject (método)'
title: ICorDebugProcess5::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
ms.openlocfilehash: 4e295e1afc19cc5b9ca763b04b05097d48f0302c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746365"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="aed44-103">ICorDebugProcess5::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="aed44-103">ICorDebugProcess5::GetObject Method</span></span>

<span data-ttu-id="aed44-104">Convierte una dirección de objeto en un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="aed44-104">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aed44-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aed44-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aed44-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aed44-106">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="aed44-107">de Dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="aed44-107">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="aed44-108">enuncia Puntero a la dirección de un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="aed44-108">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aed44-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aed44-109">Remarks</span></span>  

 <span data-ttu-id="aed44-110">Si no `addr` señala a un objeto administrado válido, el `GetObject` método devuelve `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="aed44-110">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aed44-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aed44-111">Requirements</span></span>  

 <span data-ttu-id="aed44-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aed44-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aed44-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aed44-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aed44-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aed44-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aed44-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aed44-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed44-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="aed44-116">See also</span></span>

- [<span data-ttu-id="aed44-117">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aed44-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="aed44-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="aed44-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
