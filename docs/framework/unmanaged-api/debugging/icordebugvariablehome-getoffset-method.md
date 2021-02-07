---
description: 'Más información sobre: ICorDebugVariableHome:: GetOffset (método)'
title: 'ICorDebugVariableHome:: GetOffset (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: 48b57856d2825dd2ea9328064a28783b4b36029b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728774"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="01f8b-103">ICorDebugVariableHome:: GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="01f8b-103">ICorDebugVariableHome::GetOffset Method</span></span>

<span data-ttu-id="01f8b-104">Obtiene el desplazamiento del registro base para una variable.</span><span class="sxs-lookup"><span data-stu-id="01f8b-104">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f8b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01f8b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01f8b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01f8b-106">Parameters</span></span>  

 `pOffset`  
 <span data-ttu-id="01f8b-107">enuncia Desplazamiento del registro base.</span><span class="sxs-lookup"><span data-stu-id="01f8b-107">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01f8b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="01f8b-108">Return Value</span></span>  

 <span data-ttu-id="01f8b-109">El método devuelve los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="01f8b-109">The method returns the following values:</span></span>  
  
|<span data-ttu-id="01f8b-110">Value</span><span class="sxs-lookup"><span data-stu-id="01f8b-110">Value</span></span>|<span data-ttu-id="01f8b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="01f8b-111">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="01f8b-112">La variable está en una ubicación de memoria relativa de registro.</span><span class="sxs-lookup"><span data-stu-id="01f8b-112">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="01f8b-113">La variable no está en una ubicación de memoria relativa de registro.</span><span class="sxs-lookup"><span data-stu-id="01f8b-113">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01f8b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01f8b-114">Requirements</span></span>  

 <span data-ttu-id="01f8b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01f8b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f8b-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01f8b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01f8b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01f8b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01f8b-118">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f8b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f8b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="01f8b-119">See also</span></span>

- [<span data-ttu-id="01f8b-120">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="01f8b-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
