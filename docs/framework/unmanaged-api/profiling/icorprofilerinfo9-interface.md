---
title: Interfaz ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 0ba4f2b4a515143d50bc812f04ea75d821b69471
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973805"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="6d7c5-102">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="6d7c5-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="6d7c5-103">Una subclase de [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) que proporciona métodos para consultar información sobre las funciones con varias versiones de código nativo.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="6d7c5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6d7c5-104">Methods</span></span>  

| <span data-ttu-id="6d7c5-105">Método</span><span class="sxs-lookup"><span data-stu-id="6d7c5-105">Method</span></span>|<span data-ttu-id="6d7c5-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6d7c5-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="6d7c5-107">Método GetNativeCodeStartAddresses</span><span class="sxs-lookup"><span data-stu-id="6d7c5-107">GetNativeCodeStartAddresses Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="6d7c5-108">Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="6d7c5-109">Método GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="6d7c5-109">GetILToNativeMapping3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="6d7c5-110">Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="6d7c5-111">Método GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="6d7c5-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="6d7c5-112">Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código.</span><span class="sxs-lookup"><span data-stu-id="6d7c5-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="6d7c5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d7c5-113">Requirements</span></span>  
<span data-ttu-id="6d7c5-114">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="6d7c5-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="6d7c5-115">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="6d7c5-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="6d7c5-116">**Versiones de .net:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d7c5-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="6d7c5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d7c5-117">See also</span></span>
- [<span data-ttu-id="6d7c5-118">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6d7c5-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
