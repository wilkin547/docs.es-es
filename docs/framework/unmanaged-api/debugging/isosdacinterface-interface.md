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
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420973"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="b8407-102">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="b8407-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="b8407-103">Proporciona métodos auxiliares para tener acceso a los datos de `SOS` .</span><span class="sxs-lookup"><span data-stu-id="b8407-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="b8407-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b8407-104">Methods</span></span>

| <span data-ttu-id="b8407-105">Método</span><span class="sxs-lookup"><span data-stu-id="b8407-105">Method</span></span>                                                                                                               | <span data-ttu-id="b8407-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8407-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="b8407-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="b8407-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="b8407-108">Obtiene los datos para el puntero de MethodDesc dado.</span><span class="sxs-lookup"><span data-stu-id="b8407-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="b8407-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="b8407-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="b8407-110">Recupera el puntero de la MethodDesc correspondiente al método que contiene la dirección de instrucción nativa especificada.</span><span class="sxs-lookup"><span data-stu-id="b8407-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="b8407-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="b8407-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="b8407-112">Captura los datos correspondientes al módulo cargado en una dirección determinada.</span><span class="sxs-lookup"><span data-stu-id="b8407-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b8407-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b8407-113">Remarks</span></span>

<span data-ttu-id="b8407-114">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b8407-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b8407-115">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `436f00f2-b42a-4b9f-870c-e73db66ae930` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="b8407-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8407-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8407-116">Requirements</span></span>

<span data-ttu-id="b8407-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8407-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b8407-118">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="b8407-118">**Header:** None</span></span>  
<span data-ttu-id="b8407-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="b8407-119">**Library:** None</span></span>  
<span data-ttu-id="b8407-120">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b8407-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b8407-121">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b8407-121">See also</span></span>

- [<span data-ttu-id="b8407-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="b8407-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="b8407-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b8407-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
