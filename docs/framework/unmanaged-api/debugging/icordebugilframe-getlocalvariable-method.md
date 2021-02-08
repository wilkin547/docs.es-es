---
description: 'Más información acerca de: ICorDebugILFrame:: Getlocalvariable ((método)'
title: ICorDebugILFrame::GetLocalVariable (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
ms.openlocfilehash: c4bb3e5a5d970539607efbaf55f3f7f08f7e72af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791379"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="4425f-103">ICorDebugILFrame::GetLocalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="4425f-103">ICorDebugILFrame::GetLocalVariable Method</span></span>

<span data-ttu-id="4425f-104">Obtiene el valor de la variable local especificada en este marco de pila del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4425f-104">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4425f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4425f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4425f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4425f-106">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="4425f-107">de Índice de la variable local en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="4425f-107">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4425f-108">[out] Puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.</span><span class="sxs-lookup"><span data-stu-id="4425f-108">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4425f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4425f-109">Remarks</span></span>  

 <span data-ttu-id="4425f-110">El `GetLocalVariable` método se puede utilizar en un marco de pila de MSIL o en un marco compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="4425f-110">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4425f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4425f-111">Requirements</span></span>  

 <span data-ttu-id="4425f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4425f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4425f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4425f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4425f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4425f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4425f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4425f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
