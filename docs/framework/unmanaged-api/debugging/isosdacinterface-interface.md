---
description: 'Más información acerca de: interfaz ISOSDacInterface'
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
ms.openlocfilehash: ddb99b7c6fca6870024f04933861d01e4b31ea9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790404"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="f86e7-103">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="f86e7-103">ISOSDacInterface Interface</span></span>

<span data-ttu-id="f86e7-104">Proporciona métodos auxiliares para tener acceso a los datos de `SOS` .</span><span class="sxs-lookup"><span data-stu-id="f86e7-104">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="f86e7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f86e7-105">Methods</span></span>

| <span data-ttu-id="f86e7-106">Método</span><span class="sxs-lookup"><span data-stu-id="f86e7-106">Method</span></span>                                                                                                               | <span data-ttu-id="f86e7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f86e7-107">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="f86e7-108">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="f86e7-108">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="f86e7-109">Obtiene los datos para el puntero de MethodDesc dado.</span><span class="sxs-lookup"><span data-stu-id="f86e7-109">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="f86e7-110">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="f86e7-110">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="f86e7-111">Recupera el puntero de la MethodDesc correspondiente al método que contiene la dirección de instrucción nativa especificada.</span><span class="sxs-lookup"><span data-stu-id="f86e7-111">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="f86e7-112">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="f86e7-112">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="f86e7-113">Captura los datos correspondientes al módulo cargado en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="f86e7-113">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f86e7-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f86e7-114">Remarks</span></span>

<span data-ttu-id="f86e7-115">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f86e7-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="f86e7-116">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `436f00f2-b42a-4b9f-870c-e73db66ae930` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="f86e7-116">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="f86e7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f86e7-117">Requirements</span></span>

<span data-ttu-id="f86e7-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f86e7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f86e7-119">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f86e7-119">**Header:** None</span></span>  
<span data-ttu-id="f86e7-120">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f86e7-120">**Library:** None</span></span>  
<span data-ttu-id="f86e7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f86e7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f86e7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f86e7-122">See also</span></span>

- [<span data-ttu-id="f86e7-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="f86e7-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="f86e7-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f86e7-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
