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
ms.openlocfilehash: e306834166051ae48fd283d51f18d9458091578f
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416665"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="e4baf-102">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="e4baf-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="e4baf-103">Proporciona métodos para consultar información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="e4baf-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="e4baf-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e4baf-104">Methods</span></span>

| <span data-ttu-id="e4baf-105">Método</span><span class="sxs-lookup"><span data-stu-id="e4baf-105">Method</span></span>                                                                                                                                | <span data-ttu-id="e4baf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4baf-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="e4baf-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="e4baf-107">GetMethodDefinitionByToken</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="e4baf-108">Obtiene la definición del método correspondiente a un token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="e4baf-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="e4baf-109">Solicitud</span><span class="sxs-lookup"><span data-stu-id="e4baf-109">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="e4baf-110">Solicitudes para llenar el búfer especificado con los datos del módulo.</span><span class="sxs-lookup"><span data-stu-id="e4baf-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="e4baf-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="e4baf-111">GetVersionId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="e4baf-112">Obtiene el identificador de versión. del módulo</span><span class="sxs-lookup"><span data-stu-id="e4baf-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="e4baf-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4baf-113">Remarks</span></span>

<span data-ttu-id="e4baf-114">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e4baf-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e4baf-115">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="e4baf-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4baf-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4baf-116">Requirements</span></span>

<span data-ttu-id="e4baf-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4baf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e4baf-118">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="e4baf-118">**Header:** None</span></span>  
<span data-ttu-id="e4baf-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e4baf-119">**Library:** None</span></span>  
<span data-ttu-id="e4baf-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e4baf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e4baf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4baf-121">See Also</span></span>

- [<span data-ttu-id="e4baf-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="e4baf-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="e4baf-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e4baf-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
