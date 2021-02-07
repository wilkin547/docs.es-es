---
description: 'Más información sobre: ICorDebugFrame:: GetStackRange ((método)'
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
ms.openlocfilehash: 1f1278e0c00addc3c14f4e1c8d3ed5aad0381526
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692906"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="fe065-103">ICorDebugFrame::GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="fe065-103">ICorDebugFrame::GetStackRange Method</span></span>

<span data-ttu-id="fe065-104">Obtiene el intervalo de direcciones absolutas de este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="fe065-104">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe065-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe065-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe065-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe065-106">Parameters</span></span>  

 `pStart`  
 <span data-ttu-id="fe065-107">enuncia Puntero a `CORDB_ADDRESS` que especifica la dirección de inicio del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="fe065-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="fe065-108">enuncia Puntero a `CORDB_ADDRESS` que especifica la dirección final del marco de pila representado por este `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="fe065-108">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe065-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fe065-109">Remarks</span></span>  

 <span data-ttu-id="fe065-110">El intervalo de direcciones de la pila es útil para juntar juntos los seguimientos de la pila intercalados recopilados de varios motores de depuración.</span><span class="sxs-lookup"><span data-stu-id="fe065-110">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="fe065-111">El intervalo numérico no proporciona información sobre el contenido del marco de pila.</span><span class="sxs-lookup"><span data-stu-id="fe065-111">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="fe065-112">Solo es significativo para la comparación de las ubicaciones de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="fe065-112">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe065-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe065-113">Requirements</span></span>  

 <span data-ttu-id="fe065-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe065-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe065-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe065-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe065-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe065-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe065-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe065-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
