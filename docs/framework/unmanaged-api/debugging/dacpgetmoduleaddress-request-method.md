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
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179206"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="5fa72-102">Método DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="5fa72-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="5fa72-103">Realiza una solicitud para rellenar la estructura desde la estructura de tiempo de ejecución determinada.</span><span class="sxs-lookup"><span data-stu-id="5fa72-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5fa72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fa72-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="5fa72-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fa72-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="5fa72-106">[en] Un puntero al módulo de datos de semillas.</span><span class="sxs-lookup"><span data-stu-id="5fa72-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="5fa72-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5fa72-107">Remarks</span></span>

<span data-ttu-id="5fa72-108">Esta estructura se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="5fa72-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="5fa72-109">Para usarlo, la forma más fácil es imitar la implementación:</span><span class="sxs-lookup"><span data-stu-id="5fa72-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="5fa72-110">Devuelve el valor obtenido `Request` al llamar `IXCLRDataModule*` al método en el parámetro con los siguientes parámetros:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="5fa72-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="5fa72-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fa72-111">Requirements</span></span>

<span data-ttu-id="5fa72-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fa72-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5fa72-113">**Encabezado:** Ninguna **biblioteca:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="5fa72-113">**Header:** None **Library:** None</span></span>  
<span data-ttu-id="5fa72-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa72-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5fa72-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fa72-115">See also</span></span>

- [<span data-ttu-id="5fa72-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="5fa72-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="5fa72-117">Interfaz DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="5fa72-117">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
