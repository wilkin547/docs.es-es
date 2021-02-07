---
description: 'Más información acerca de: ICorDebugValue:: método se obtiene'
title: ICorDebugValue::GetSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 3fc2582990d58fa2e42f240dfd3e563eed34e372
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690345"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="1beb3-103">ICorDebugValue::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="1beb3-103">ICorDebugValue::GetSize Method</span></span>

<span data-ttu-id="1beb3-104">Obtiene el tamaño, en bytes, de este objeto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="1beb3-104">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1beb3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1beb3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1beb3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1beb3-106">Parameters</span></span>  

 `pSize`  
 <span data-ttu-id="1beb3-107">enuncia Tamaño, en bytes, de este objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="1beb3-107">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1beb3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1beb3-108">Remarks</span></span>  

 <span data-ttu-id="1beb3-109">Si el tipo del valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="1beb3-109">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="1beb3-110">El `ICorDebugValue::GetSize` método devuelve `COR_E_OVERFLOW` para objetos mayores de 4 GB en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="1beb3-110">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="1beb3-111">Use el método [icordebugvalue3 (:: getsize64 (](icordebugvalue3-getsize64-method.md) en lugar de los objetos mayores de 4 GB.</span><span class="sxs-lookup"><span data-stu-id="1beb3-111">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1beb3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1beb3-112">Requirements</span></span>  

 <span data-ttu-id="1beb3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1beb3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1beb3-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1beb3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1beb3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1beb3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1beb3-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1beb3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1beb3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1beb3-117">See also</span></span>

- [<span data-ttu-id="1beb3-118">Método GetSize64</span><span class="sxs-lookup"><span data-stu-id="1beb3-118">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
