---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: 10f06fb04099ef947711bc7c5641e5a7f1fa36b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695720"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="a2734-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)</span><span class="sxs-lookup"><span data-stu-id="a2734-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>

<span data-ttu-id="a2734-103">Obtiene el valor de un argumento o una variable local que se almacena en los dos registros especificados para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="a2734-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2734-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2734-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2734-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2734-105">Parameters</span></span>  

 `highWordReg`  
 <span data-ttu-id="a2734-106">de Un valor de la enumeración "CorDebugRegister (" que especifica el registro que contiene la palabra alta del valor.</span><span class="sxs-lookup"><span data-stu-id="a2734-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="a2734-107">de Un valor de la `CorDebugRegister` enumeración que especifica el registro que contiene la palabra baja del valor.</span><span class="sxs-lookup"><span data-stu-id="a2734-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="a2734-108">de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a2734-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a2734-109">de `PCCOR_SIGNATURE` Valor que apunta a la firma de metadatos binarios del tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="a2734-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a2734-110">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en los registros especificados.</span><span class="sxs-lookup"><span data-stu-id="a2734-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2734-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2734-111">Remarks</span></span>  

 <span data-ttu-id="a2734-112">El `GetLocalDoubleRegisterValue` método se puede utilizar en un marco nativo o en un marco compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="a2734-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2734-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2734-113">Requirements</span></span>  

 <span data-ttu-id="a2734-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2734-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2734-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2734-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2734-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2734-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2734-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2734-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2734-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a2734-118">See also</span></span>
