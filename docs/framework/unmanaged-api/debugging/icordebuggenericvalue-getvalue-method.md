---
description: 'Más información sobre: ICorDebugGenericValue:: GetValue (método)'
title: ICorDebugGenericValue::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
ms.openlocfilehash: 9c8459ce6a9fb59e934b1ebd355aa091a37b2d7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661069"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="0c8c7-103">ICorDebugGenericValue::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="0c8c7-103">ICorDebugGenericValue::GetValue Method</span></span>

<span data-ttu-id="0c8c7-104">Copia el valor de este genérico en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="0c8c7-104">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8c7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c8c7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c8c7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c8c7-106">Parameters</span></span>  

 `pTo`  
 <span data-ttu-id="0c8c7-107">enuncia Puntero al valor representado por este objeto ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="0c8c7-107">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="0c8c7-108">El valor puede ser un tipo simple o un tipo de referencia (es decir, un puntero).</span><span class="sxs-lookup"><span data-stu-id="0c8c7-108">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c8c7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c8c7-109">Requirements</span></span>  

 <span data-ttu-id="0c8c7-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c8c7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c8c7-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c8c7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c8c7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c8c7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c8c7-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c8c7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
