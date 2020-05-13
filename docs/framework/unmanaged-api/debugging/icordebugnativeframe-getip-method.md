---
title: ICorDebugNativeFrame::GetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: 53576ca938074fb7e5974a96bb53a84cb6ed67ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213600"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="75e26-102">ICorDebugNativeFrame::GetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="75e26-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="75e26-103">Obtiene la ubicación de desplazamiento del código nativo en la que está establecido actualmente el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="75e26-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75e26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75e26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75e26-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="75e26-106">enuncia Puntero a la ubicación de desplazamiento en el código nativo.</span><span class="sxs-lookup"><span data-stu-id="75e26-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75e26-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="75e26-107">Remarks</span></span>  
 <span data-ttu-id="75e26-108">Si el marco de pila representado por este "ICorDebugNativeFrame" está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="75e26-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="75e26-109">Si este marco de pila no está activo, el desplazamiento es la dirección de la siguiente instrucción que se va a ejecutar cuando se reactive el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="75e26-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e26-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75e26-110">Requirements</span></span>  
 <span data-ttu-id="75e26-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75e26-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e26-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75e26-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75e26-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75e26-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75e26-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e26-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e26-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75e26-115">See also</span></span>
