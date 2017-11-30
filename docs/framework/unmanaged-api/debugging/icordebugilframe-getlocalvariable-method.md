---
title: "ICorDebugILFrame::GetLocalVariable (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetLocalVariable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 24b4ed62c3fb68306683d2199f901ec510f0da6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="18690-102">ICorDebugILFrame::GetLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="18690-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="18690-103">Obtiene el valor de la variable local especificada en este marco de pila de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18690-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18690-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18690-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18690-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="18690-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="18690-106">[in] El índice de la variable local en este marco de pila MSIL.</span><span class="sxs-lookup"><span data-stu-id="18690-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="18690-107">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="18690-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18690-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18690-108">Remarks</span></span>  
 <span data-ttu-id="18690-109">El `GetLocalVariable` método se puede utilizar en un marco de pila MSIL o en un marco compilado just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="18690-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18690-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18690-110">Requirements</span></span>  
 <span data-ttu-id="18690-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18690-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18690-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18690-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18690-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18690-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18690-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18690-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
