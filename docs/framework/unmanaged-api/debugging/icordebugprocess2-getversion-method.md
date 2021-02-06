---
description: 'Más información sobre: ICorDebugProcess2:: GetVersion (método)'
title: ICorDebugProcess2::GetVersion (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
ms.openlocfilehash: 8472e811ea4df1f99fb4e27b55f3561fae0c8a21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650110"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="b7ec3-103">ICorDebugProcess2::GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="b7ec3-103">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="b7ec3-104">Obtiene el número de versión del Common Language Runtime (CLR) que se ejecuta en este proceso.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-104">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7ec3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7ec3-105">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="b7ec3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7ec3-106">Parameters</span></span>

`version`\
<span data-ttu-id="b7ec3-107">enuncia Puntero a una estructura de COR_VERSION que almacena el número de versión del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-107">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7ec3-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7ec3-108">Remarks</span></span>

<span data-ttu-id="b7ec3-109">El `GetVersion` método devuelve un código de error si no se ha cargado ningún tiempo de ejecución en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b7ec3-109">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7ec3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7ec3-110">Requirements</span></span>

<span data-ttu-id="b7ec3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ec3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b7ec3-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7ec3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="b7ec3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7ec3-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b7ec3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ec3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
