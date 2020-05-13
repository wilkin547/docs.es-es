---
title: ICorDebugILFrame::GetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: 3890cb4236f113bc6efc23bfb606d19a525ec234
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210272"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="37b12-102">ICorDebugILFrame::GetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="37b12-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="37b12-103">Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="37b12-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b12-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37b12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37b12-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37b12-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="37b12-106">enuncia Valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="37b12-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="37b12-107">enuncia Puntero a una combinación bit a bit de los valores de enumeración de CorDebugMappingResult (que describen cómo se obtuvo el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="37b12-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37b12-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37b12-108">Remarks</span></span>  
 <span data-ttu-id="37b12-109">El valor del puntero de instrucción es el desplazamiento del marco de pila en el código del lenguaje intermedio de Microsoft (MSIL) de la función.</span><span class="sxs-lookup"><span data-stu-id="37b12-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="37b12-110">Si el marco de pila está activo, esta dirección es la siguiente instrucción que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="37b12-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="37b12-111">Si el marco de pila no está activo, esta dirección es la siguiente instrucción que se debe ejecutar cuando se reactive el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="37b12-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="37b12-112">Si este marco es un marco compilado Just-in-Time (JIT), el valor del puntero de instrucción estará determinado por la asignación hacia atrás desde el puntero de instrucción nativo real, por lo que el valor puede ser solo aproximado.</span><span class="sxs-lookup"><span data-stu-id="37b12-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37b12-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37b12-113">Requirements</span></span>  
 <span data-ttu-id="37b12-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37b12-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b12-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37b12-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37b12-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37b12-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37b12-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b12-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
