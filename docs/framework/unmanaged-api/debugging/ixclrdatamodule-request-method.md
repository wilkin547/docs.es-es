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
ms.openlocfilehash: 336e47d531fc880571165cd55f117825cd1a2abb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374874"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="5f9a8-102">Método IXCLRDataModule::Request</span><span class="sxs-lookup"><span data-stu-id="5f9a8-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="5f9a8-103">Solicitudes para llenar el búfer especificado con los datos del módulo.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5f9a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f9a8-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a><span data-ttu-id="5f9a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f9a8-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="5f9a8-106">[in] Tipo de solicitud en enviarse.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="5f9a8-107">[in] tamaño del búfer de entrada que se pasarán en.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="5f9a8-108">[in, size_is(inBufferSize)] Puntero de búfer para los datos sin procesar que se enviarán en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="5f9a8-109">[in] Tamaño del búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="5f9a8-110">[out, size_is(outBufferSize)] Puntero de búfer que usará para almacenar la respuesta de solicitud.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f9a8-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f9a8-111">Remarks</span></span>

<span data-ttu-id="5f9a8-112">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura de la tabla de métodos virtuales 36th.</span><span class="sxs-lookup"><span data-stu-id="5f9a8-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f9a8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f9a8-113">Requirements</span></span>

<span data-ttu-id="5f9a8-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f9a8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5f9a8-115">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="5f9a8-115">**Header:** None</span></span>   
<span data-ttu-id="5f9a8-116">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5f9a8-116">**Library:** None</span></span>  
<span data-ttu-id="5f9a8-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5f9a8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5f9a8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f9a8-118">See also</span></span>
- [<span data-ttu-id="5f9a8-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="5f9a8-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="5f9a8-120">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="5f9a8-120">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)