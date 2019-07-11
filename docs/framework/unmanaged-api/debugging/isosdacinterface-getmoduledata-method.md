---
title: Método ISOSDacInterface::GetModuleData
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 97b297def9fba329ff6d9573f7b2e7cc811273f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764718"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="a9333-102">Método ISOSDacInterface::GetModuleData</span><span class="sxs-lookup"><span data-stu-id="a9333-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="a9333-103">Captura los datos correspondientes al módulo cargado en una dirección dada.</span><span class="sxs-lookup"><span data-stu-id="a9333-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a9333-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9333-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="a9333-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9333-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="a9333-106">[in] La dirección del módulo para recuperar información.</span><span class="sxs-lookup"><span data-stu-id="a9333-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="a9333-107">[out] El [DacpModuleData estructura](dacpmoduledata-structure.md) para contener la información del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="a9333-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9333-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9333-108">Remarks</span></span>

<span data-ttu-id="a9333-109">El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura de 13 de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="a9333-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a9333-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9333-110">Requirements</span></span>

<span data-ttu-id="a9333-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9333-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a9333-112">**Encabezado**: None</span><span class="sxs-lookup"><span data-stu-id="a9333-112">**Header:** None</span></span>  
<span data-ttu-id="a9333-113">**Biblioteca:** None</span><span class="sxs-lookup"><span data-stu-id="a9333-113">**Library:** None</span></span>  
<span data-ttu-id="a9333-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a9333-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a9333-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9333-115">See also</span></span>

- [<span data-ttu-id="a9333-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="a9333-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="a9333-117">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="a9333-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
