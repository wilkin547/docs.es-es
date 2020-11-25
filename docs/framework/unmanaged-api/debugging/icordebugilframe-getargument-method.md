---
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
ms.openlocfilehash: d17179dbeb9564b16c0c95a43502a53a67d3b9b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703170"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="dff1e-102">ICorDebugILFrame::GetArgument (Método)</span><span class="sxs-lookup"><span data-stu-id="dff1e-102">ICorDebugILFrame::GetArgument Method</span></span>

<span data-ttu-id="dff1e-103">Obtiene el valor del argumento especificado en este marco de pila del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="dff1e-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dff1e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dff1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dff1e-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="dff1e-106">de Índice del argumento de este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="dff1e-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="dff1e-107">[out] Puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="dff1e-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dff1e-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dff1e-108">Remarks</span></span>  

 <span data-ttu-id="dff1e-109">El `GetArgument` método se puede utilizar en un marco de pila de MSIL o en un marco compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="dff1e-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dff1e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dff1e-110">Requirements</span></span>  

 <span data-ttu-id="dff1e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dff1e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dff1e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dff1e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dff1e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dff1e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dff1e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff1e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
