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
ms.openlocfilehash: 39f5c1813b08f4d72c610820b1434e29eb4aec8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121275"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="4e653-102">ICorDebugProcess5::GetTypeForTypeID (Método)</span><span class="sxs-lookup"><span data-stu-id="4e653-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="4e653-103">Convierte un identificador de tipo en un valor de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="4e653-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e653-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e653-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e653-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e653-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="4e653-106">de El identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="4e653-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="4e653-107">enuncia Puntero a la dirección de un objeto ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="4e653-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e653-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e653-108">Remarks</span></span>  
 <span data-ttu-id="4e653-109">En algunos casos, los métodos que devuelven un identificador de tipo pueden devolver un valor de `COR_TYPEID` null.</span><span class="sxs-lookup"><span data-stu-id="4e653-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="4e653-110">Si este valor se pasa como el argumento `id`, se producirá un error en el método `GetTypeForTypeID` y se devolverá `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="4e653-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e653-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e653-111">Requirements</span></span>  
 <span data-ttu-id="4e653-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e653-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e653-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e653-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e653-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e653-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e653-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e653-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e653-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e653-116">See also</span></span>

- [<span data-ttu-id="4e653-117">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e653-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="4e653-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4e653-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
