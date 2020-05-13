---
title: ICorDebugFrame::GetStackRange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: cacdccf5c27cd1d115134d49e754b4ace2870b72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205155"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="f1fd7-102">ICorDebugFrame::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="f1fd7-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="f1fd7-103">Obtiene el intervalo de direcciones absolutas de este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f1fd7-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1fd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1fd7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1fd7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1fd7-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="f1fd7-106">enuncia Puntero a `CORDB_ADDRESS` que especifica la dirección de inicio del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="f1fd7-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="f1fd7-107">enuncia Puntero a `CORDB_ADDRESS` que especifica la dirección final del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="f1fd7-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1fd7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f1fd7-108">Remarks</span></span>  
 <span data-ttu-id="f1fd7-109">El intervalo de direcciones de la pila es útil para juntar juntos los seguimientos de la pila intercalados recopilados de varios motores de depuración.</span><span class="sxs-lookup"><span data-stu-id="f1fd7-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="f1fd7-110">El intervalo numérico no proporciona información sobre el contenido del marco de pila.</span><span class="sxs-lookup"><span data-stu-id="f1fd7-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="f1fd7-111">Solo es significativo para la comparación de las ubicaciones de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="f1fd7-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1fd7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1fd7-112">Requirements</span></span>  
 <span data-ttu-id="f1fd7-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1fd7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1fd7-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1fd7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1fd7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1fd7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1fd7-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1fd7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
