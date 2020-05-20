---
title: 'ISOSDacInterface:: GetModuleData (método)'
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
ms.openlocfilehash: b302100eb6cbfa83896cd358762c496ea01f7509
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420986"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="2d877-102">ISOSDacInterface:: GetModuleData (método)</span><span class="sxs-lookup"><span data-stu-id="2d877-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="2d877-103">Captura los datos correspondientes al módulo cargado en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="2d877-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2d877-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d877-104">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="2d877-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d877-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="2d877-106">de Dirección del módulo para el que se va a recuperar información.</span><span class="sxs-lookup"><span data-stu-id="2d877-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="2d877-107">enuncia [Estructura DacpModuleData](dacpmoduledata-structure.md) que contiene la información del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="2d877-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d877-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2d877-108">Remarks</span></span>

<span data-ttu-id="2d877-109">El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura decimocuarta de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="2d877-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d877-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d877-110">Requirements</span></span>

<span data-ttu-id="2d877-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d877-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2d877-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="2d877-112">**Header:** None</span></span>  
<span data-ttu-id="2d877-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="2d877-113">**Library:** None</span></span>  
<span data-ttu-id="2d877-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d877-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2d877-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2d877-115">See also</span></span>

- [<span data-ttu-id="2d877-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="2d877-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="2d877-117">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="2d877-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
