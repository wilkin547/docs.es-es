---
title: Interfaz ISOSDacInterface
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ccaf479fc4fb90007b4999e95ee03bdd0529321e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922153"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="f4396-102">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="f4396-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="f4396-103">Proporciona métodos auxiliares para acceder a ellos desde `SOS`.</span><span class="sxs-lookup"><span data-stu-id="f4396-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="f4396-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4396-104">Methods</span></span>

| <span data-ttu-id="f4396-105">Método</span><span class="sxs-lookup"><span data-stu-id="f4396-105">Method</span></span>                                                                                                               | <span data-ttu-id="f4396-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4396-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="f4396-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="f4396-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="f4396-108">Obtiene los datos para el puntero de MethodDesc determinado.</span><span class="sxs-lookup"><span data-stu-id="f4396-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="f4396-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="f4396-109">GetMethodDescPtrFromIP</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="f4396-110">Recupera el puntero de la MethodDesc correspondiente del método que contiene la dirección de instrucción nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="f4396-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="f4396-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="f4396-111">GetModuleData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="f4396-112">Captura los datos correspondientes al módulo cargado en una dirección dada.</span><span class="sxs-lookup"><span data-stu-id="f4396-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f4396-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4396-113">Remarks</span></span>

<span data-ttu-id="f4396-114">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f4396-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f4396-115">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="f4396-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="f4396-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4396-116">Requirements</span></span>

<span data-ttu-id="f4396-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4396-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f4396-118">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="f4396-118">**Header:** None</span></span>  
<span data-ttu-id="f4396-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f4396-119">**Library:** None</span></span>  
<span data-ttu-id="f4396-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f4396-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f4396-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4396-121">See also</span></span>

- [<span data-ttu-id="f4396-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="f4396-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="f4396-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f4396-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
