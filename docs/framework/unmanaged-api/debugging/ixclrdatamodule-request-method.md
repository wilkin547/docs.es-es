---
title: Método IXCLRDataModule::Request
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
ms.openlocfilehash: 755063ca6da29a2e4733dd653306192ac0434ec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775458"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="f00f5-102">Método IXCLRDataModule::Request</span><span class="sxs-lookup"><span data-stu-id="f00f5-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="f00f5-103">Solicitudes para llenar el búfer especificado con los datos del módulo.</span><span class="sxs-lookup"><span data-stu-id="f00f5-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f00f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f00f5-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="f00f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f00f5-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="f00f5-106">[in] Tipo de solicitud en enviarse.</span><span class="sxs-lookup"><span data-stu-id="f00f5-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="f00f5-107">[in] tamaño del búfer de entrada que se pasarán en.</span><span class="sxs-lookup"><span data-stu-id="f00f5-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="f00f5-108">[in, size_is(inBufferSize)] Puntero de búfer para los datos sin procesar que se enviarán en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f00f5-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="f00f5-109">[in] Tamaño del búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="f00f5-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="f00f5-110">[out, size_is(outBufferSize)] Puntero de búfer que usará para almacenar la respuesta de solicitud.</span><span class="sxs-lookup"><span data-stu-id="f00f5-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="f00f5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f00f5-111">Remarks</span></span>

<span data-ttu-id="f00f5-112">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura de la tabla de métodos virtuales 36th.</span><span class="sxs-lookup"><span data-stu-id="f00f5-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f00f5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f00f5-113">Requirements</span></span>

<span data-ttu-id="f00f5-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f00f5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="f00f5-115">**Encabezado**: Ninguno **biblioteca:** Ninguno **versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f00f5-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f00f5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f00f5-116">See also</span></span>

- [<span data-ttu-id="f00f5-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="f00f5-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="f00f5-118">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="f00f5-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)