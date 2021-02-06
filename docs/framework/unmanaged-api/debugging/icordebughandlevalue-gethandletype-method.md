---
description: 'Más información sobre: ICorDebugHandleValue:: Gethandletype ((método)'
title: ICorDebugHandleValue::GetHandleType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
ms.openlocfilehash: 708d60cd8116cf3f0fdc436a34d863380be2543d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660965"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="ac488-103">ICorDebugHandleValue::GetHandleType (Método)</span><span class="sxs-lookup"><span data-stu-id="ac488-103">ICorDebugHandleValue::GetHandleType Method</span></span>

<span data-ttu-id="ac488-104">Obtiene un valor que indica el tipo de identificador al que hace referencia este objeto ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="ac488-104">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac488-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac488-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac488-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac488-106">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="ac488-107">enuncia Un puntero a un valor de la enumeración CorDebugHandleType (que indica el tipo de este identificador.</span><span class="sxs-lookup"><span data-stu-id="ac488-107">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac488-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac488-108">Requirements</span></span>  

 <span data-ttu-id="ac488-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac488-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac488-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac488-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac488-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac488-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac488-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac488-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
