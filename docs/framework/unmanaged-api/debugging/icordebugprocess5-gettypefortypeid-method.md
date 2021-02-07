---
description: 'Más información sobre: ICorDebugProcess5:: Gettypefortypeid ((método)'
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
ms.openlocfilehash: a18543b0afc867dc3796264ac1d08a775c73ca59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746378"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="19401-103">ICorDebugProcess5::GetTypeForTypeID (Método)</span><span class="sxs-lookup"><span data-stu-id="19401-103">ICorDebugProcess5::GetTypeForTypeID Method</span></span>

<span data-ttu-id="19401-104">Convierte un identificador de tipo en un valor de ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="19401-104">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19401-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19401-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19401-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19401-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="19401-107">de El identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="19401-107">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="19401-108">enuncia Puntero a la dirección de un objeto ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="19401-108">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19401-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="19401-109">Remarks</span></span>  

 <span data-ttu-id="19401-110">En algunos casos, los métodos que devuelven un identificador de tipo pueden devolver un `COR_TYPEID` valor null.</span><span class="sxs-lookup"><span data-stu-id="19401-110">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="19401-111">Si este valor se pasa como `id` argumento, el `GetTypeForTypeID` método producirá un error y devolverá `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="19401-111">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19401-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19401-112">Requirements</span></span>  

 <span data-ttu-id="19401-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19401-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19401-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19401-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19401-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19401-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19401-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19401-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19401-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="19401-117">See also</span></span>

- [<span data-ttu-id="19401-118">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19401-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="19401-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="19401-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
