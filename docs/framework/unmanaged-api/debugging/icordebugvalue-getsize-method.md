---
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
ms.openlocfilehash: 9ff7128f55236ae4d0c3a9067a279c496cfb6798
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396751"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="b62f9-102">ICorDebugValue::GetSize (Método)</span><span class="sxs-lookup"><span data-stu-id="b62f9-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="b62f9-103">Obtiene el tamaño, en bytes, de este objeto "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="b62f9-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b62f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b62f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b62f9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b62f9-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="b62f9-106">enuncia Tamaño, en bytes, de este objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="b62f9-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b62f9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b62f9-107">Remarks</span></span>  
 <span data-ttu-id="b62f9-108">Si el tipo del valor es un tipo de referencia, este método devuelve el tamaño del puntero en lugar del tamaño del objeto.</span><span class="sxs-lookup"><span data-stu-id="b62f9-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="b62f9-109">El `ICorDebugValue::GetSize` método devuelve `COR_E_OVERFLOW` para objetos mayores de 4 GB en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b62f9-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="b62f9-110">Use el método [icordebugvalue3 (:: getsize64 (](icordebugvalue3-getsize64-method.md) en lugar de los objetos mayores de 4 GB.</span><span class="sxs-lookup"><span data-stu-id="b62f9-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b62f9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b62f9-111">Requirements</span></span>  
 <span data-ttu-id="b62f9-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b62f9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b62f9-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b62f9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b62f9-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b62f9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b62f9-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b62f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b62f9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b62f9-116">See also</span></span>

- [<span data-ttu-id="b62f9-117">Método GetSize64</span><span class="sxs-lookup"><span data-stu-id="b62f9-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
