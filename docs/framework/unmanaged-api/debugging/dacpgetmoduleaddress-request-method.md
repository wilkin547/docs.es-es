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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102912"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="c3db1-102">Método DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="c3db1-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="c3db1-103">Realiza una solicitud para rellenar la estructura desde la estructura de tiempo de ejecución determinada.</span><span class="sxs-lookup"><span data-stu-id="c3db1-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c3db1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3db1-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="c3db1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3db1-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="c3db1-106">[en] Un puntero al módulo de datos de semillas.</span><span class="sxs-lookup"><span data-stu-id="c3db1-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3db1-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c3db1-107">Remarks</span></span>

<span data-ttu-id="c3db1-108">Esta estructura se encuentra dentro del tiempo de ejecución y no se expone a través de encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c3db1-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c3db1-109">Para usarlo, la forma más fácil es imitar la implementación:</span><span class="sxs-lookup"><span data-stu-id="c3db1-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="c3db1-110">Devuelve el valor obtenido `Request` al llamar `IXCLRDataModule*` al método en el parámetro con los siguientes parámetros:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="c3db1-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="c3db1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3db1-111">Requirements</span></span>

<span data-ttu-id="c3db1-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="c3db1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md)</span></span>\
<span data-ttu-id="c3db1-113">**Encabezado:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="c3db1-113">**Header:** None\</span></span>
<span data-ttu-id="c3db1-114">**Biblioteca:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="c3db1-114">**Library:** None\</span></span>
<span data-ttu-id="c3db1-115">**Versiones de .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3db1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c3db1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3db1-116">See also</span></span>

- [<span data-ttu-id="c3db1-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="c3db1-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="c3db1-118">Estructura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="c3db1-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
