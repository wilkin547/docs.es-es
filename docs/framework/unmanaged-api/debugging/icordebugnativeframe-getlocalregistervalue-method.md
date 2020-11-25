---
title: ICorDebugNativeFrame::GetLocalRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
ms.openlocfilehash: a90bba4a4dc9ca92ccdc4af1636d194f92fd7373
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695730"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="40eb3-102">ICorDebugNativeFrame::GetLocalRegisterValue (Método)</span><span class="sxs-lookup"><span data-stu-id="40eb3-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>

<span data-ttu-id="40eb3-103">Obtiene el valor de un argumento o una variable local que se almacena en el registro especificado para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="40eb3-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40eb3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40eb3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40eb3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40eb3-105">Parameters</span></span>  

 `reg`  
 <span data-ttu-id="40eb3-106">de Un valor de la enumeración "CorDebugRegister (" que especifica el registro que contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="40eb3-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="40eb3-107">de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="40eb3-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="40eb3-108">de `PCCOR_SIGNATURE` Valor que apunta a la firma de metadatos binarios del tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="40eb3-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="40eb3-109">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en el registro especificado.</span><span class="sxs-lookup"><span data-stu-id="40eb3-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40eb3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40eb3-110">Remarks</span></span>  

 <span data-ttu-id="40eb3-111">El `GetLocalRegisterValue` método se puede utilizar en un marco nativo o en un marco compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="40eb3-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40eb3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40eb3-112">Requirements</span></span>  

 <span data-ttu-id="40eb3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40eb3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40eb3-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40eb3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40eb3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40eb3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40eb3-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40eb3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40eb3-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40eb3-117">See also</span></span>
