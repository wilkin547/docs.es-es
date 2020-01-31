---
title: ICorDebugProcess5::GetTypeForTypeID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
ms.openlocfilehash: bb25c9235e4fcded5c230d2d417b9d41bbdd9b19
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792337"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="c101b-102">ICorDebugProcess5::GetTypeForTypeID (Método)</span><span class="sxs-lookup"><span data-stu-id="c101b-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="c101b-103">Convierte un identificador de tipo en un valor de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="c101b-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c101b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c101b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c101b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c101b-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="c101b-106">de El identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="c101b-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="c101b-107">enuncia Puntero a la dirección de un objeto ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="c101b-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c101b-108">Notas</span><span class="sxs-lookup"><span data-stu-id="c101b-108">Remarks</span></span>  
 <span data-ttu-id="c101b-109">En algunos casos, los métodos que devuelven un identificador de tipo pueden devolver un valor de `COR_TYPEID` null.</span><span class="sxs-lookup"><span data-stu-id="c101b-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="c101b-110">Si este valor se pasa como el argumento `id`, se producirá un error en el método `GetTypeForTypeID` y se devolverá `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="c101b-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c101b-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c101b-111">Requirements</span></span>  
 <span data-ttu-id="c101b-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c101b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c101b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c101b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c101b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c101b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c101b-115">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c101b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c101b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c101b-116">See also</span></span>

- [<span data-ttu-id="c101b-117">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c101b-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="c101b-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c101b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
