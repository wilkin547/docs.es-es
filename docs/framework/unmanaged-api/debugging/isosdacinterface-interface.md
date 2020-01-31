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
ms.openlocfilehash: 94349a3f7b18c8ce29bb3a71cb9d10ee4eac8036
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790476"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="12582-102">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="12582-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="12582-103">Proporciona métodos auxiliares para tener acceso a los datos de `SOS`.</span><span class="sxs-lookup"><span data-stu-id="12582-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="12582-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="12582-104">Methods</span></span>

| <span data-ttu-id="12582-105">Método</span><span class="sxs-lookup"><span data-stu-id="12582-105">Method</span></span>                                                                                                               | <span data-ttu-id="12582-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="12582-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="12582-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="12582-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="12582-108">Obtiene los datos para el puntero de MethodDesc dado.</span><span class="sxs-lookup"><span data-stu-id="12582-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="12582-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="12582-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="12582-110">Recupera el puntero de la MethodDesc correspondiente al método que contiene la dirección de instrucción nativa especificada.</span><span class="sxs-lookup"><span data-stu-id="12582-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="12582-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="12582-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="12582-112">Captura los datos correspondientes al módulo cargado en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="12582-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="12582-113">Notas</span><span class="sxs-lookup"><span data-stu-id="12582-113">Remarks</span></span>

<span data-ttu-id="12582-114">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="12582-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="12582-115">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` que se puede obtener a través de los mecanismos COM habituales.</span><span class="sxs-lookup"><span data-stu-id="12582-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="12582-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="12582-116">Requirements</span></span>

<span data-ttu-id="12582-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12582-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="12582-118">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="12582-118">**Header:** None</span></span>  
<span data-ttu-id="12582-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="12582-119">**Library:** None</span></span>  
<span data-ttu-id="12582-120">**.NET Framework versiones:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="12582-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="12582-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="12582-121">See also</span></span>

- [<span data-ttu-id="12582-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="12582-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="12582-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="12582-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
