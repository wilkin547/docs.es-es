---
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
ms.openlocfilehash: 75a165e2fd517f36d779a934a5bdd9c41956411a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396760"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="db3b8-102">ICorDebugVariableHome:: GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="db3b8-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="db3b8-103">Obtiene el desplazamiento del registro base para una variable.</span><span class="sxs-lookup"><span data-stu-id="db3b8-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db3b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db3b8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db3b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db3b8-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="db3b8-106">enuncia Desplazamiento del registro base.</span><span class="sxs-lookup"><span data-stu-id="db3b8-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db3b8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db3b8-107">Return Value</span></span>  
 <span data-ttu-id="db3b8-108">El método devuelve los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db3b8-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="db3b8-109">Valor</span><span class="sxs-lookup"><span data-stu-id="db3b8-109">Value</span></span>|<span data-ttu-id="db3b8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="db3b8-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="db3b8-111">La variable está en una ubicación de memoria relativa de registro.</span><span class="sxs-lookup"><span data-stu-id="db3b8-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="db3b8-112">La variable no está en una ubicación de memoria relativa de registro.</span><span class="sxs-lookup"><span data-stu-id="db3b8-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db3b8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db3b8-113">Requirements</span></span>  
 <span data-ttu-id="db3b8-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db3b8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db3b8-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db3b8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db3b8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db3b8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db3b8-117">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db3b8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3b8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="db3b8-118">See also</span></span>

- [<span data-ttu-id="db3b8-119">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="db3b8-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
