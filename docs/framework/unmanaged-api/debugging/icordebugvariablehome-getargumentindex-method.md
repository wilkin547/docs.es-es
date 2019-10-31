---
title: 'ICorDebugVariableHome:: GetArgumentIndex (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 86b2815c6f95c674c49bba7455e8497192bd8bac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125149"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="a86de-102">ICorDebugVariableHome:: GetArgumentIndex (método)</span><span class="sxs-lookup"><span data-stu-id="a86de-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="a86de-103">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="a86de-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="a86de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a86de-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="a86de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a86de-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="a86de-106">enuncia Puntero al índice del argumento.</span><span class="sxs-lookup"><span data-stu-id="a86de-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="a86de-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a86de-107">Return Value</span></span>

<span data-ttu-id="a86de-108">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="a86de-108">The method returns the following values.</span></span>

|<span data-ttu-id="a86de-109">Valor</span><span class="sxs-lookup"><span data-stu-id="a86de-109">Value</span></span>|<span data-ttu-id="a86de-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a86de-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="a86de-111">La llamada al método devolvió un índice de argumento válido.</span><span class="sxs-lookup"><span data-stu-id="a86de-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="a86de-112">La instancia de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) actual representa una variable local.</span><span class="sxs-lookup"><span data-stu-id="a86de-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a86de-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a86de-113">Remarks</span></span>

<span data-ttu-id="a86de-114">El índice de argumento se puede utilizar para recuperar los metadatos de este argumento.</span><span class="sxs-lookup"><span data-stu-id="a86de-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="a86de-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a86de-115">Requirements</span></span>

<span data-ttu-id="a86de-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a86de-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a86de-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a86de-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="a86de-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a86de-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a86de-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a86de-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a86de-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a86de-120">See also</span></span>

- [<span data-ttu-id="a86de-121">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a86de-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
