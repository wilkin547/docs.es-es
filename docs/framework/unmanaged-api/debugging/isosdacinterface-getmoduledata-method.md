---
description: 'Más información sobre: ISOSDacInterface:: GetModuleData (método)'
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
ms.openlocfilehash: c01f55d55d5ee9082dee4b3adb3022bb17807aa2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790391"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="30343-103">ISOSDacInterface:: GetModuleData (método)</span><span class="sxs-lookup"><span data-stu-id="30343-103">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="30343-104">Captura los datos correspondientes al módulo cargado en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="30343-104">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="30343-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30343-105">Syntax</span></span>

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="30343-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30343-106">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="30343-107">de Dirección del módulo para el que se va a recuperar información.</span><span class="sxs-lookup"><span data-stu-id="30343-107">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="30343-108">enuncia [Estructura DacpModuleData](dacpmoduledata-structure.md) que contiene la información del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="30343-108">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="30343-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="30343-109">Remarks</span></span>

<span data-ttu-id="30343-110">El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura decimocuarta de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="30343-110">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="30343-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30343-111">Requirements</span></span>

<span data-ttu-id="30343-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30343-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="30343-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="30343-113">**Header:** None</span></span>  
<span data-ttu-id="30343-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="30343-114">**Library:** None</span></span>  
<span data-ttu-id="30343-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="30343-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="30343-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="30343-116">See also</span></span>

- [<span data-ttu-id="30343-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="30343-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="30343-118">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="30343-118">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
