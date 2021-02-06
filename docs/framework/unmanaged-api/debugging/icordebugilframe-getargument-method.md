---
description: 'Más información acerca de: ICorDebugILFrame:: Getargument ((método)'
title: ICorDebugILFrame::GetArgument (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: c845f3c07502f3b1ce564833ee6ef98e3305463f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650526"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="28e5e-103">ICorDebugILFrame::GetArgument (Método)</span><span class="sxs-lookup"><span data-stu-id="28e5e-103">ICorDebugILFrame::GetArgument Method</span></span>

<span data-ttu-id="28e5e-104">Obtiene el valor del argumento especificado en este marco de pila del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="28e5e-104">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e5e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28e5e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28e5e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28e5e-106">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="28e5e-107">de Índice del argumento de este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="28e5e-107">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="28e5e-108">[out] Puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="28e5e-108">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28e5e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="28e5e-109">Remarks</span></span>  

 <span data-ttu-id="28e5e-110">El `GetArgument` método se puede utilizar en un marco de pila de MSIL o en un marco compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="28e5e-110">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28e5e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28e5e-111">Requirements</span></span>  

 <span data-ttu-id="28e5e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28e5e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28e5e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28e5e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28e5e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28e5e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28e5e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28e5e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
