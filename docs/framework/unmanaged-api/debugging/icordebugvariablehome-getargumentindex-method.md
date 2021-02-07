---
description: 'Más información sobre: ICorDebugVariableHome:: GetArgumentIndex (método)'
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
ms.openlocfilehash: 827ef55d3e3509cbfbfc8213ef5b53fbe2e2220e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690046"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="bc855-103">ICorDebugVariableHome:: GetArgumentIndex (método)</span><span class="sxs-lookup"><span data-stu-id="bc855-103">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="bc855-104">Obtiene el índice de un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="bc855-104">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc855-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc855-105">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="bc855-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc855-106">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="bc855-107">enuncia Puntero al índice del argumento.</span><span class="sxs-lookup"><span data-stu-id="bc855-107">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="bc855-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bc855-108">Return Value</span></span>

<span data-ttu-id="bc855-109">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="bc855-109">The method returns the following values.</span></span>

|<span data-ttu-id="bc855-110">Value</span><span class="sxs-lookup"><span data-stu-id="bc855-110">Value</span></span>|<span data-ttu-id="bc855-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc855-111">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="bc855-112">La llamada al método devolvió un índice de argumento válido.</span><span class="sxs-lookup"><span data-stu-id="bc855-112">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="bc855-113">La instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) actual representa una variable local.</span><span class="sxs-lookup"><span data-stu-id="bc855-113">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bc855-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc855-114">Remarks</span></span>

<span data-ttu-id="bc855-115">El índice de argumento se puede utilizar para recuperar los metadatos de este argumento.</span><span class="sxs-lookup"><span data-stu-id="bc855-115">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="bc855-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc855-116">Requirements</span></span>

<span data-ttu-id="bc855-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc855-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bc855-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc855-118">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="bc855-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc855-119">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="bc855-120">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc855-120">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bc855-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc855-121">See also</span></span>

- [<span data-ttu-id="bc855-122">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="bc855-122">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
