---
description: 'Más información sobre: DacpGetModuleAddress:: Request (método)'
title: Método DacpGetModuleAddress::Request
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4cdec9cf6b9bd818ce1137fb5b2c691532fab94e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801506"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="05ee8-103">Método DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="05ee8-103">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="05ee8-104">Realiza una solicitud para rellenar la estructura a partir de la estructura en tiempo de ejecución especificada.</span><span class="sxs-lookup"><span data-stu-id="05ee8-104">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="05ee8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05ee8-105">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="05ee8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05ee8-106">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="05ee8-107">de Un puntero al módulo de datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="05ee8-107">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="05ee8-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="05ee8-108">Remarks</span></span>

<span data-ttu-id="05ee8-109">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="05ee8-109">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="05ee8-110">Para usarlo, la manera más fácil es imitar la implementación:</span><span class="sxs-lookup"><span data-stu-id="05ee8-110">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="05ee8-111">Devuelva el valor obtenido de la llamada al `Request` método en el `IXCLRDataModule*` parámetro con los parámetros siguientes: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="05ee8-111">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="05ee8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05ee8-112">Requirements</span></span>

<span data-ttu-id="05ee8-113">**Plataformas:** Consulte [los requisitos del sistema](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="05ee8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="05ee8-114">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="05ee8-114">**Header:** None\</span></span>
<span data-ttu-id="05ee8-115">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="05ee8-115">**Library:** None\</span></span>
<span data-ttu-id="05ee8-116">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="05ee8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="05ee8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="05ee8-117">See also</span></span>

- [<span data-ttu-id="05ee8-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="05ee8-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="05ee8-119">Estructura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="05ee8-119">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
