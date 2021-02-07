---
description: 'Más información acerca de: interfaz ICorProfilerInfo9'
title: Interfaz ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 954cb16d2b789359693f6a8fa3e0f6e19ad19b3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736913"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="3fe35-103">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="3fe35-103">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="3fe35-104">Una subclase de [ICorProfilerInfo8](icorprofilerinfo8-interface.md) que proporciona métodos para consultar información sobre las funciones con varias versiones de código nativo.</span><span class="sxs-lookup"><span data-stu-id="3fe35-104">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="3fe35-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3fe35-105">Methods</span></span>  

| <span data-ttu-id="3fe35-106">Método</span><span class="sxs-lookup"><span data-stu-id="3fe35-106">Method</span></span>|<span data-ttu-id="3fe35-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fe35-107">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="3fe35-108">Método GetNativeCodeStartAddresses</span><span class="sxs-lookup"><span data-stu-id="3fe35-108">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="3fe35-109">Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.</span><span class="sxs-lookup"><span data-stu-id="3fe35-109">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="3fe35-110">Método GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="3fe35-110">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="3fe35-111">Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.</span><span class="sxs-lookup"><span data-stu-id="3fe35-111">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="3fe35-112">Método GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="3fe35-112">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="3fe35-113">Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código.</span><span class="sxs-lookup"><span data-stu-id="3fe35-113">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="3fe35-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fe35-114">Requirements</span></span>  

<span data-ttu-id="3fe35-115">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="3fe35-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="3fe35-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3fe35-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="3fe35-117">**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe35-117">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3fe35-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fe35-118">See also</span></span>

- [<span data-ttu-id="3fe35-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="3fe35-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
