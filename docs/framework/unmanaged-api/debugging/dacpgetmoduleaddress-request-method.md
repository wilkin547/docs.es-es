---
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
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860836"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="e2f70-102">Método DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="e2f70-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="e2f70-103">Realiza una solicitud para rellenar la estructura a partir de la estructura en tiempo de ejecución especificada.</span><span class="sxs-lookup"><span data-stu-id="e2f70-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e2f70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2f70-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="e2f70-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2f70-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="e2f70-106">de Un puntero al módulo de datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="e2f70-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="e2f70-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2f70-107">Remarks</span></span>

<span data-ttu-id="e2f70-108">Esta estructura reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e2f70-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e2f70-109">Para usarlo, la manera más fácil es imitar la implementación:</span><span class="sxs-lookup"><span data-stu-id="e2f70-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="e2f70-110">Devuelva el valor obtenido de la `Request` llamada al método `IXCLRDataModule*` en el parámetro con los parámetros siguientes:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="e2f70-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="e2f70-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2f70-111">Requirements</span></span>

<span data-ttu-id="e2f70-112">**Plataformas:** Consulte [los requisitos del sistema](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e2f70-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="e2f70-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e2f70-113">**Header:** None\</span></span>
<span data-ttu-id="e2f70-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e2f70-114">**Library:** None\</span></span>
<span data-ttu-id="e2f70-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e2f70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e2f70-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2f70-116">See also</span></span>

- [<span data-ttu-id="e2f70-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="e2f70-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="e2f70-118">Estructura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="e2f70-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
