---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 861b31e5621e9a7b40403d249c6a5c8c4ac25db8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501045"
---
# <a name="cor_prf_assembly_reference_info-structure"></a><span data-ttu-id="dd185-102">COR_PRF_ASSEMBLY_REFERENCE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="dd185-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="dd185-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="dd185-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dd185-104">Proporciona a Common Language Runtime información sobre una referencia de ensamblado que debe tener en cuenta a la hora de realizar un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dd185-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd185-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd185-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="dd185-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="dd185-106">Members</span></span>  
  
|<span data-ttu-id="dd185-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="dd185-107">Member</span></span>|<span data-ttu-id="dd185-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd185-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="dd185-109">Puntero a la clave pública o token del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dd185-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="dd185-110">Número de bytes en la clave pública o token.</span><span class="sxs-lookup"><span data-stu-id="dd185-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="dd185-111">Nombre del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="dd185-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="dd185-112">Puntero a los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dd185-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="dd185-113">Puntero a un objeto binario grande (BLOB) de hash.</span><span class="sxs-lookup"><span data-stu-id="dd185-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="dd185-114">Número de bytes en el BLOB de hash.</span><span class="sxs-lookup"><span data-stu-id="dd185-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="dd185-115">Marcas del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dd185-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd185-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd185-116">Remarks</span></span>  
 <span data-ttu-id="dd185-117">El generador de perfiles rellena la estructura `COR_PRF_EX_CLAUSE_INFO` cuando declara referencias de ensamblado adicionales que Common Language Runtime debe tener en cuenta al realizar un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dd185-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="dd185-118">Si el generador de perfiles se registra para el método de devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , el tiempo de ejecución pasa la ruta de acceso y el nombre del ensamblado que se va a cargar, junto con un puntero a un objeto de interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a ese método.</span><span class="sxs-lookup"><span data-stu-id="dd185-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="dd185-119">Después, el generador de perfiles puede llamar al método [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` objeto para cada ensamblado de destino al que tiene previsto hacer referencia desde el ensamblado especificado en la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dd185-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd185-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd185-120">Requirements</span></span>  
 <span data-ttu-id="dd185-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd185-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd185-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dd185-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dd185-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd185-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd185-124">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd185-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd185-125">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="dd185-125">See also</span></span>

- [<span data-ttu-id="dd185-126">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="dd185-126">Profiling Structures</span></span>](profiling-structures.md)
- [<span data-ttu-id="dd185-127">GetAssemblyReferences (método)</span><span class="sxs-lookup"><span data-stu-id="dd185-127">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="dd185-128">Método AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="dd185-128">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
