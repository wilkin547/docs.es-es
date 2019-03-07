---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5696dc8fcf4b5c84e12ca60f93679f7b67d5f7e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476326"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="94a9a-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)</span><span class="sxs-lookup"><span data-stu-id="94a9a-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>
<span data-ttu-id="94a9a-103">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="94a9a-103">Retrieves a generic dictionary map.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94a9a-104">Syntax</span></span>  
  
```  
HRESULT GetGenericDictionaryInfo(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94a9a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94a9a-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="94a9a-106">[out] Un puntero a la dirección de un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) objeto que contiene la asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="94a9a-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="94a9a-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="94a9a-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94a9a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94a9a-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94a9a-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="94a9a-109">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="94a9a-110">La asignación se compone de dos secciones de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="94a9a-110">The map consists of two top-level sections:</span></span>  
  
-   <span data-ttu-id="94a9a-111">Un [directory](#Directory) que contiene las direcciones virtuales relativas (RVA) de todos los diccionarios incluidos en esta asignación.</span><span class="sxs-lookup"><span data-stu-id="94a9a-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>  
  
-   <span data-ttu-id="94a9a-112">Una alineación de bytes [montón](#Heap) que contiene información de la creación de instancias de objeto.</span><span class="sxs-lookup"><span data-stu-id="94a9a-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="94a9a-113">Se inicia inmediatamente después de la última entrada de directorio.</span><span class="sxs-lookup"><span data-stu-id="94a9a-113">It starts immediately after the last directory entry.</span></span>  
  
<a name="Directory"></a>   
## <a name="the-directory"></a><span data-ttu-id="94a9a-114">El directorio</span><span class="sxs-lookup"><span data-stu-id="94a9a-114">The Directory</span></span>  
 <span data-ttu-id="94a9a-115">Cada entrada del directorio hace referencia a un desplazamiento dentro del montón; es decir, es un desplazamiento relativo al inicio del montón.</span><span class="sxs-lookup"><span data-stu-id="94a9a-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="94a9a-116">El valor de las entradas individuales no es necesariamente único; varias entradas de directorio pueden apuntar al mismo desplazamiento en el montón.</span><span class="sxs-lookup"><span data-stu-id="94a9a-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>  
  
 <span data-ttu-id="94a9a-117">La parte del directorio de la asignación del diccionario genérico tiene la estructura siguiente:</span><span class="sxs-lookup"><span data-stu-id="94a9a-117">The directory portion of the generic dictionary map has the following structure:</span></span>  
  
-   <span data-ttu-id="94a9a-118">Los primeros cuatro bytes contienen el número de entradas del diccionario (es decir, el número de direcciones virtuales relativas en el diccionario).</span><span class="sxs-lookup"><span data-stu-id="94a9a-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="94a9a-119">Nos referiremos a este valor como *N*. Si se establece el bit alto, las entradas se ordenan por la dirección virtual relativa en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="94a9a-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>  
  
-   <span data-ttu-id="94a9a-120">El *N* siguen las entradas de directorio.</span><span class="sxs-lookup"><span data-stu-id="94a9a-120">The *N* directory entries follow.</span></span> <span data-ttu-id="94a9a-121">Cada entrada consta de 8 bytes, en dos segmentos de 4 bytes:</span><span class="sxs-lookup"><span data-stu-id="94a9a-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>  
  
    -   <span data-ttu-id="94a9a-122">Bytes 0-3: RVA; dirección virtual relativa del diccionario.</span><span class="sxs-lookup"><span data-stu-id="94a9a-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>  
  
    -   <span data-ttu-id="94a9a-123">Bytes 4-7: Desplazamiento; un desplazamiento relativo al inicio del montón.</span><span class="sxs-lookup"><span data-stu-id="94a9a-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>  
  
<a name="Heap"></a>   
## <a name="the-heap"></a><span data-ttu-id="94a9a-124">El montón</span><span class="sxs-lookup"><span data-stu-id="94a9a-124">The Heap</span></span>  
 <span data-ttu-id="94a9a-125">El tamaño del montón se puede calcular con un lector de secuencias restando la longitud de la secuencia del tamaño del directorio + 4.</span><span class="sxs-lookup"><span data-stu-id="94a9a-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="94a9a-126">En otras palabras:</span><span class="sxs-lookup"><span data-stu-id="94a9a-126">In other words:</span></span>  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 <span data-ttu-id="94a9a-127">donde el tamaño del directorio es `N * 8`.</span><span class="sxs-lookup"><span data-stu-id="94a9a-127">where the directory size is `N * 8`.</span></span>  
  
 <span data-ttu-id="94a9a-128">El formato de cada elemento de información sobre la creación de instancias en el montón es:</span><span class="sxs-lookup"><span data-stu-id="94a9a-128">The format for each instantiation information item on the heap is:</span></span>  
  
-   <span data-ttu-id="94a9a-129">La longitud de este elemento de información sobre la creación de instancias en bytes, en el formato de metadatos ECMA comprimido.</span><span class="sxs-lookup"><span data-stu-id="94a9a-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="94a9a-130">El valor excluye esta información de longitud.</span><span class="sxs-lookup"><span data-stu-id="94a9a-130">The value excludes this length information.</span></span>  
  
-   <span data-ttu-id="94a9a-131">El número de tipos de creación de instancias genérica, o *T*, en formato de metadatos ECMA comprimido.</span><span class="sxs-lookup"><span data-stu-id="94a9a-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>  
  
-   <span data-ttu-id="94a9a-132">*T* tipos, cada uno representado en el formato de firma del tipo ECMA.</span><span class="sxs-lookup"><span data-stu-id="94a9a-132">*T* types, each represented in ECMA type signature format.</span></span>  
  
 <span data-ttu-id="94a9a-133">Incluir la longitud de cada elemento del montón permite la ordenación simple de la sección del directorio sin afectar al montón.</span><span class="sxs-lookup"><span data-stu-id="94a9a-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94a9a-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94a9a-134">Requirements</span></span>  
 <span data-ttu-id="94a9a-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a9a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a9a-136">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94a9a-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94a9a-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94a9a-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94a9a-138">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a9a-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a9a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="94a9a-139">See also</span></span>
- [<span data-ttu-id="94a9a-140">ICorDebugSymbolProvider2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94a9a-140">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="94a9a-141">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="94a9a-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
