---
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
ms.openlocfilehash: e4d297023d96de83965c3d04ca9efe2613fd54d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084443"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="cf661-102">ICorDebugProcess5::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="cf661-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="cf661-103">Convierte una dirección de objeto en un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="cf661-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf661-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf661-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf661-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf661-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="cf661-106">de Dirección del objeto.</span><span class="sxs-lookup"><span data-stu-id="cf661-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="cf661-107">enuncia Puntero a la dirección de un objeto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="cf661-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf661-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf661-108">Remarks</span></span>  
 <span data-ttu-id="cf661-109">Si `addr` no apunta a un objeto administrado válido, el método `GetObject` devuelve `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="cf661-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf661-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf661-110">Requirements</span></span>  
 <span data-ttu-id="cf661-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf661-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf661-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf661-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf661-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf661-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf661-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf661-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf661-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf661-115">See also</span></span>

- [<span data-ttu-id="cf661-116">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf661-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="cf661-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cf661-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
