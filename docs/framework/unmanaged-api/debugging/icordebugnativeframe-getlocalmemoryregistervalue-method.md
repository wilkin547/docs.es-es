---
description: 'Más información acerca de: ICorDebugNativeFrame:: Getlocalmemoryregistervalue ((método)'
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
ms.openlocfilehash: a0858aa11713bb71c485174c2f1624a0c7cda821
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718036"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="ea8ae-103">ICorDebugNativeFrame::GetLocalMemoryRegisterValue (Método)</span><span class="sxs-lookup"><span data-stu-id="ea8ae-103">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>

<span data-ttu-id="ea8ae-104">Obtiene el valor de un argumento o una variable local, de la que la palabra baja y la palabra alta se almacenan en el registro y la ubicación de memoria especificados, respectivamente, para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-104">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea8ae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea8ae-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea8ae-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea8ae-106">Parameters</span></span>  

 `highWordAddress`  
 <span data-ttu-id="ea8ae-107">de `CORDB_ADDRESS` Valor que especifica la ubicación de memoria que contiene la palabra alta del valor.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="ea8ae-108">de Un valor de la enumeración "CorDebugRegister (" que especifica el registro que contiene la palabra baja del valor.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-108">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ea8ae-109">de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-109">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ea8ae-110">de `PCCOR_SIGNATURE` Valor que apunta a la firma de metadatos binarios del tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-110">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ea8ae-111">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en el registro y la ubicación de memoria especificados.</span><span class="sxs-lookup"><span data-stu-id="ea8ae-111">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea8ae-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea8ae-112">Requirements</span></span>  

 <span data-ttu-id="ea8ae-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea8ae-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8ae-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea8ae-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea8ae-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea8ae-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea8ae-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea8ae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8ae-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea8ae-117">See also</span></span>
