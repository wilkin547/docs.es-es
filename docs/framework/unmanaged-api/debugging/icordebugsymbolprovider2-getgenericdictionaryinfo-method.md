---
title: "ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0c4192c94d70bd9406607d645716e4dd6f8b957
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="39fec-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)</span><span class="sxs-lookup"><span data-stu-id="39fec-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>
<span data-ttu-id="39fec-103">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="39fec-103">Retrieves a generic dictionary map.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39fec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39fec-104">Syntax</span></span>  
  
```  
HRESULT GetGenericDictionaryInfo(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39fec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39fec-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="39fec-106">[out] Un puntero a la dirección de un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) objeto que contiene la asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="39fec-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="39fec-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="39fec-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39fec-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39fec-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39fec-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="39fec-109">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="39fec-110">La asignación se compone de dos secciones de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="39fec-110">The map consists of two top-level sections:</span></span>  
  
-   <span data-ttu-id="39fec-111">A [directory](#Directory) que contiene las direcciones virtuales relativas (RVA) de todos los diccionarios incluidos en esta asignación.</span><span class="sxs-lookup"><span data-stu-id="39fec-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>  
  
-   <span data-ttu-id="39fec-112">Alineación bytes [montón](#Heap) que contiene información sobre la creación de instancias de objetos.</span><span class="sxs-lookup"><span data-stu-id="39fec-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="39fec-113">Se inicia inmediatamente después de la última entrada de directorio.</span><span class="sxs-lookup"><span data-stu-id="39fec-113">It starts immediately after the last directory entry.</span></span>  
  
<a name="Directory"></a>   
## <a name="the-directory"></a><span data-ttu-id="39fec-114">El directorio</span><span class="sxs-lookup"><span data-stu-id="39fec-114">The Directory</span></span>  
 <span data-ttu-id="39fec-115">Cada entrada del directorio hace referencia a un desplazamiento dentro del montón; es decir, es un desplazamiento relativo al inicio del montón.</span><span class="sxs-lookup"><span data-stu-id="39fec-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="39fec-116">El valor de las entradas individuales no es necesariamente único; varias entradas de directorio pueden apuntar al mismo desplazamiento en el montón.</span><span class="sxs-lookup"><span data-stu-id="39fec-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>  
  
 <span data-ttu-id="39fec-117">La parte del directorio de la asignación del diccionario genérico tiene la estructura siguiente:</span><span class="sxs-lookup"><span data-stu-id="39fec-117">The directory portion of the generic dictionary map has the following structure:</span></span>  
  
-   <span data-ttu-id="39fec-118">Los primeros cuatro bytes contienen el número de entradas del diccionario (es decir, el número de direcciones virtuales relativas en el diccionario).</span><span class="sxs-lookup"><span data-stu-id="39fec-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="39fec-119">Nos referiremos a este valor como *N*. Si se establece el bit alto, las entradas se ordenan por la dirección virtual relativa en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="39fec-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>  
  
-   <span data-ttu-id="39fec-120">El *N* siguen entradas de directorio.</span><span class="sxs-lookup"><span data-stu-id="39fec-120">The *N* directory entries follow.</span></span> <span data-ttu-id="39fec-121">Cada entrada consta de 8 bytes, en dos segmentos de 4 bytes:</span><span class="sxs-lookup"><span data-stu-id="39fec-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>  
  
    -   <span data-ttu-id="39fec-122">Bytes de 0 a 3: RVA; dirección virtual relativa del diccionario.</span><span class="sxs-lookup"><span data-stu-id="39fec-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>  
  
    -   <span data-ttu-id="39fec-123">Bytes de 4 a 7: desplazamiento; un desplazamiento relativo al inicio del montón.</span><span class="sxs-lookup"><span data-stu-id="39fec-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>  
  
<a name="Heap"></a>   
## <a name="the-heap"></a><span data-ttu-id="39fec-124">El montón</span><span class="sxs-lookup"><span data-stu-id="39fec-124">The Heap</span></span>  
 <span data-ttu-id="39fec-125">El tamaño del montón se puede calcular con un lector de secuencias restando la longitud de la secuencia del tamaño del directorio + 4.</span><span class="sxs-lookup"><span data-stu-id="39fec-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="39fec-126">En otras palabras:</span><span class="sxs-lookup"><span data-stu-id="39fec-126">In other words:</span></span>  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 <span data-ttu-id="39fec-127">donde el tamaño del directorio es `N * 8`.</span><span class="sxs-lookup"><span data-stu-id="39fec-127">where the directory size is `N * 8`.</span></span>  
  
 <span data-ttu-id="39fec-128">El formato de cada elemento de información sobre la creación de instancias en el montón es:</span><span class="sxs-lookup"><span data-stu-id="39fec-128">The format for each instantiation information item on the heap is:</span></span>  
  
-   <span data-ttu-id="39fec-129">La longitud de este elemento de información sobre la creación de instancias en bytes, en el formato de metadatos ECMA comprimido.</span><span class="sxs-lookup"><span data-stu-id="39fec-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="39fec-130">El valor excluye esta información de longitud.</span><span class="sxs-lookup"><span data-stu-id="39fec-130">The value excludes this length information.</span></span>  
  
-   <span data-ttu-id="39fec-131">El número de tipos genéricos de la creación de instancias, o *T*, en formato de metadatos ECMA comprimido.</span><span class="sxs-lookup"><span data-stu-id="39fec-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>  
  
-   <span data-ttu-id="39fec-132">*T* tipos, cada uno representado en el formato de firma de tipo ECMA.</span><span class="sxs-lookup"><span data-stu-id="39fec-132">*T* types, each represented in ECMA type signature format.</span></span>  
  
 <span data-ttu-id="39fec-133">Incluir la longitud de cada elemento del montón permite la ordenación simple de la sección del directorio sin afectar al montón.</span><span class="sxs-lookup"><span data-stu-id="39fec-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39fec-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39fec-134">Requirements</span></span>  
 <span data-ttu-id="39fec-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39fec-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39fec-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39fec-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39fec-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39fec-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39fec-138">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39fec-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39fec-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="39fec-139">See Also</span></span>  
 [<span data-ttu-id="39fec-140">ICorDebugSymbolProvider2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39fec-140">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [<span data-ttu-id="39fec-141">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="39fec-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
