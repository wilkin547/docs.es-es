---
title: "ICorDebugILFrame::GetArgument (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetArgument
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 592354f11faac1fb4d5b050a096f4eab04643c0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="81b67-102">ICorDebugILFrame::GetArgument (Método)</span><span class="sxs-lookup"><span data-stu-id="81b67-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="81b67-103">Obtiene el valor del argumento especificado en este marco de pila de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="81b67-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81b67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81b67-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81b67-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81b67-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="81b67-106">[in] El índice del argumento en este marco de pila MSIL.</span><span class="sxs-lookup"><span data-stu-id="81b67-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="81b67-107">[out] Un puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="81b67-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81b67-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81b67-108">Remarks</span></span>  
 <span data-ttu-id="81b67-109">El `GetArgument` método se puede utilizar en un marco de pila MSIL o en un marco compilado just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="81b67-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81b67-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81b67-110">Requirements</span></span>  
 <span data-ttu-id="81b67-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81b67-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81b67-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81b67-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81b67-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81b67-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81b67-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81b67-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
