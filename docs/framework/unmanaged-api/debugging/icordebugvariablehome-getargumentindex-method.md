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
ms.openlocfilehash: 27a676fd1d2d7903943e44f8a7201b88af4fba89
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396993"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="d86ab-102">ICorDebugVariableHome:: GetArgumentIndex (método)</span><span class="sxs-lookup"><span data-stu-id="d86ab-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="d86ab-103">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="d86ab-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="d86ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d86ab-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="d86ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d86ab-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="d86ab-106">enuncia Puntero al índice del argumento.</span><span class="sxs-lookup"><span data-stu-id="d86ab-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="d86ab-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d86ab-107">Return Value</span></span>

<span data-ttu-id="d86ab-108">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="d86ab-108">The method returns the following values.</span></span>

|<span data-ttu-id="d86ab-109">Valor</span><span class="sxs-lookup"><span data-stu-id="d86ab-109">Value</span></span>|<span data-ttu-id="d86ab-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d86ab-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="d86ab-111">La llamada al método devolvió un índice de argumento válido.</span><span class="sxs-lookup"><span data-stu-id="d86ab-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="d86ab-112">La instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) actual representa una variable local.</span><span class="sxs-lookup"><span data-stu-id="d86ab-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d86ab-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d86ab-113">Remarks</span></span>

<span data-ttu-id="d86ab-114">El índice de argumento se puede utilizar para recuperar los metadatos de este argumento.</span><span class="sxs-lookup"><span data-stu-id="d86ab-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="d86ab-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d86ab-115">Requirements</span></span>

<span data-ttu-id="d86ab-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d86ab-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d86ab-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d86ab-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="d86ab-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d86ab-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d86ab-119">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d86ab-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d86ab-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d86ab-120">See also</span></span>

- [<span data-ttu-id="d86ab-121">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="d86ab-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
