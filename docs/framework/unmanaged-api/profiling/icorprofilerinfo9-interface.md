---
title: Interfaz ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: af6bd02c6d4e88c72dca20d2520d1ecc8cf1c421
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928782"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="a08ae-102">Interfaz ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="a08ae-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="a08ae-103">Una subclase de [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) que proporciona métodos para consultar información sobre las funciones con varias versiones de código nativo.</span><span class="sxs-lookup"><span data-stu-id="a08ae-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="a08ae-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a08ae-104">Methods</span></span>  

| <span data-ttu-id="a08ae-105">Método</span><span class="sxs-lookup"><span data-stu-id="a08ae-105">Method</span></span>|<span data-ttu-id="a08ae-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a08ae-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="a08ae-107">Método GetNativeCodeStartAddresses</span><span class="sxs-lookup"><span data-stu-id="a08ae-107">GetNativeCodeStartAddresses Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="a08ae-108">Dado un functionId y rejitId, enumera la dirección de inicio del código nativo de todas las versiones de JIT de este código que existen actualmente.</span><span class="sxs-lookup"><span data-stu-id="a08ae-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="a08ae-109">Método GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="a08ae-109">GetILToNativeMapping3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="a08ae-110">Dada la dirección de inicio del código nativo, devuelve la información de asignación nativa a IL para esta versión JIT del código.</span><span class="sxs-lookup"><span data-stu-id="a08ae-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="a08ae-111">Método GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="a08ae-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="a08ae-112">Dada la dirección de inicio del código nativo, devuelve los bloques de memoria virtual que almacenan este código.</span><span class="sxs-lookup"><span data-stu-id="a08ae-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="a08ae-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a08ae-113">Requirements</span></span>  
<span data-ttu-id="a08ae-114">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="a08ae-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="a08ae-115">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="a08ae-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="a08ae-116">**Versiones de .net:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a08ae-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a08ae-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a08ae-117">See also</span></span>

- [<span data-ttu-id="a08ae-118">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a08ae-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
