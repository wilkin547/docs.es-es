---
description: 'Más información sobre: IXCLRDataModule:: Request (método)'
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
ms.openlocfilehash: 96f4153c58a228cfb22a5cd25a53b6e60fc4dfd1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800739"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="d9e52-103">IXCLRDataModule:: Request (método)</span><span class="sxs-lookup"><span data-stu-id="d9e52-103">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="d9e52-104">Solicita que rellene el búfer proporcionado con los datos del módulo.</span><span class="sxs-lookup"><span data-stu-id="d9e52-104">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d9e52-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9e52-105">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="d9e52-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9e52-106">Parameters</span></span>

`reqCode`\
<span data-ttu-id="d9e52-107">de Tipo de solicitud que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="d9e52-107">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="d9e52-108">[in] tamaño del búfer de entrada que se va a pasar.</span><span class="sxs-lookup"><span data-stu-id="d9e52-108">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="d9e52-109">[in, size_is (inBufferSize)] Puntero de búfer para los datos sin procesar que se van a enviar en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d9e52-109">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="d9e52-110">de Tamaño del búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="d9e52-110">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="d9e52-111">[out, size_is (outBufferSize)] Puntero de búfer que se utiliza para almacenar la respuesta de solicitud.</span><span class="sxs-lookup"><span data-stu-id="d9e52-111">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9e52-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d9e52-112">Remarks</span></span>

<span data-ttu-id="d9e52-113">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura 37th de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="d9e52-113">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 37th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d9e52-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9e52-114">Requirements</span></span>

<span data-ttu-id="d9e52-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9e52-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="d9e52-116">**Encabezado:** Ninguna **biblioteca:** ninguna **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e52-116">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d9e52-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9e52-117">See also</span></span>

- [<span data-ttu-id="d9e52-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="d9e52-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="d9e52-119">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="d9e52-119">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
