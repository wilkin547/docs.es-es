---
title: Interfaz ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 371e85ce8f5d7b420a30ac842ec658949e47d30e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861650"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="97c1b-102">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="97c1b-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="97c1b-103">Una subclase de [ICorProfilerInfo8](icorprofilerinfo8-interface.md) que proporciona métodos para consultar información sobre las funciones con varias versiones de código nativo.</span><span class="sxs-lookup"><span data-stu-id="97c1b-103">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="97c1b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="97c1b-104">Methods</span></span>  

| <span data-ttu-id="97c1b-105">Método</span><span class="sxs-lookup"><span data-stu-id="97c1b-105">Method</span></span>|<span data-ttu-id="97c1b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="97c1b-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="97c1b-107">Método GetNativeCodeStartAddresses</span><span class="sxs-lookup"><span data-stu-id="97c1b-107">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="97c1b-108">Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.</span><span class="sxs-lookup"><span data-stu-id="97c1b-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="97c1b-109">Método GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="97c1b-109">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="97c1b-110">Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.</span><span class="sxs-lookup"><span data-stu-id="97c1b-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="97c1b-111">Método GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="97c1b-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="97c1b-112">Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código.</span><span class="sxs-lookup"><span data-stu-id="97c1b-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="97c1b-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="97c1b-113">Requirements</span></span>  
<span data-ttu-id="97c1b-114">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="97c1b-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="97c1b-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97c1b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="97c1b-116">**Versiones de .net:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97c1b-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="97c1b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="97c1b-117">See also</span></span>

- [<span data-ttu-id="97c1b-118">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="97c1b-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
