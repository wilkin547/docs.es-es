---
description: 'Más información acerca de: interfaz IXCLRDataModule'
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
ms.openlocfilehash: 403d4dd3db64f2855347562da7217a3562985c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800752"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="71f1e-103">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="71f1e-103">IXCLRDataModule Interface</span></span>

<span data-ttu-id="71f1e-104">Proporciona métodos para consultar información sobre un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="71f1e-104">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="71f1e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="71f1e-105">Methods</span></span>

| <span data-ttu-id="71f1e-106">Método</span><span class="sxs-lookup"><span data-stu-id="71f1e-106">Method</span></span>                                                                                                                                | <span data-ttu-id="71f1e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="71f1e-107">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="71f1e-108">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="71f1e-108">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="71f1e-109">Obtiene la definición de método correspondiente a un token de metadatos determinado.</span><span class="sxs-lookup"><span data-stu-id="71f1e-109">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="71f1e-110">Solicitud</span><span class="sxs-lookup"><span data-stu-id="71f1e-110">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="71f1e-111">Solicita que rellene el búfer proporcionado con los datos del módulo.</span><span class="sxs-lookup"><span data-stu-id="71f1e-111">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="71f1e-112">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="71f1e-112">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="71f1e-113">Obtiene el identificador de versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="71f1e-113">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="71f1e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="71f1e-114">Remarks</span></span>

<span data-ttu-id="71f1e-115">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="71f1e-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="71f1e-116">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="71f1e-116">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="71f1e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71f1e-117">Requirements</span></span>

<span data-ttu-id="71f1e-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71f1e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="71f1e-119">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="71f1e-119">**Header:** None</span></span>  
<span data-ttu-id="71f1e-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="71f1e-120">**Library:** None</span></span>  
<span data-ttu-id="71f1e-121">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="71f1e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="71f1e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="71f1e-122">See also</span></span>

- [<span data-ttu-id="71f1e-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="71f1e-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="71f1e-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="71f1e-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
