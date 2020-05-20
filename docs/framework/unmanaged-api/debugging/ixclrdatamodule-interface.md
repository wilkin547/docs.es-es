---
title: Interfaz IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3c2bc771c0a131329b9403c99a33ca7b79023771
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420856"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="5a300-102">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="5a300-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="5a300-103">Proporciona métodos para consultar información sobre un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="5a300-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="5a300-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a300-104">Methods</span></span>

| <span data-ttu-id="5a300-105">Método</span><span class="sxs-lookup"><span data-stu-id="5a300-105">Method</span></span>                                                                                                                                | <span data-ttu-id="5a300-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a300-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="5a300-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="5a300-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="5a300-108">Obtiene la definición de método correspondiente a un token de metadatos determinado.</span><span class="sxs-lookup"><span data-stu-id="5a300-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="5a300-109">Solicitud</span><span class="sxs-lookup"><span data-stu-id="5a300-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="5a300-110">Solicita que rellene el búfer proporcionado con los datos del módulo.</span><span class="sxs-lookup"><span data-stu-id="5a300-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="5a300-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="5a300-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="5a300-112">Obtiene el identificador de versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="5a300-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="5a300-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a300-113">Remarks</span></span>

<span data-ttu-id="5a300-114">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="5a300-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="5a300-115">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="5a300-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a300-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a300-116">Requirements</span></span>

<span data-ttu-id="5a300-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a300-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5a300-118">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5a300-118">**Header:** None</span></span>  
<span data-ttu-id="5a300-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5a300-119">**Library:** None</span></span>  
<span data-ttu-id="5a300-120">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5a300-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5a300-121">Consulta también</span><span class="sxs-lookup"><span data-stu-id="5a300-121">See also</span></span>

- [<span data-ttu-id="5a300-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="5a300-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="5a300-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5a300-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
