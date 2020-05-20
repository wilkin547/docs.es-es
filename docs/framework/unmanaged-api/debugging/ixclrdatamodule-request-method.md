---
title: 'IXCLRDataModule:: Request (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3c18fc5c947cbb89fc4e9aed60d3cedcbe22d749
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420817"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="2a7bf-102">IXCLRDataModule:: Request (método)</span><span class="sxs-lookup"><span data-stu-id="2a7bf-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="2a7bf-103">Solicita que rellene el búfer proporcionado con los datos del módulo.</span><span class="sxs-lookup"><span data-stu-id="2a7bf-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2a7bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a7bf-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="2a7bf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a7bf-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="2a7bf-106">de Tipo de solicitud que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="2a7bf-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="2a7bf-107">[in] tamaño del búfer de entrada que se va a pasar.</span><span class="sxs-lookup"><span data-stu-id="2a7bf-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="2a7bf-108">[in, size_is (inBufferSize)] Puntero de búfer para los datos sin procesar que se van a enviar en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2a7bf-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="2a7bf-109">de Tamaño del búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="2a7bf-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="2a7bf-110">[out, size_is (outBufferSize)] Puntero de búfer que se utiliza para almacenar la respuesta de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2a7bf-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a7bf-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a7bf-111">Remarks</span></span>

<span data-ttu-id="2a7bf-112">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura 37th de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="2a7bf-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 37th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a7bf-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a7bf-113">Requirements</span></span>

<span data-ttu-id="2a7bf-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a7bf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="2a7bf-115">**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a7bf-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2a7bf-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2a7bf-116">See also</span></span>

- [<span data-ttu-id="2a7bf-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="2a7bf-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="2a7bf-118">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="2a7bf-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
