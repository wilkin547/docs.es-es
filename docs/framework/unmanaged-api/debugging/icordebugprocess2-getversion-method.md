---
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
ms.openlocfilehash: 391b848d3b3f66f6af6bf3adbefb6e94d526e748
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213509"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="ede99-102">ICorDebugProcess2::GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="ede99-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="ede99-103">Obtiene el número de versión del Common Language Runtime (CLR) que se ejecuta en este proceso.</span><span class="sxs-lookup"><span data-stu-id="ede99-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="ede99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ede99-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="ede99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ede99-105">Parameters</span></span>

`version`\
<span data-ttu-id="ede99-106">enuncia Puntero a una estructura de COR_VERSION que almacena el número de versión del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ede99-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="ede99-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ede99-107">Remarks</span></span>

<span data-ttu-id="ede99-108">El `GetVersion` método devuelve un código de error si no se ha cargado ningún tiempo de ejecución en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ede99-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="ede99-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ede99-109">Requirements</span></span>

<span data-ttu-id="ede99-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ede99-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ede99-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ede99-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="ede99-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ede99-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ede99-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ede99-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
