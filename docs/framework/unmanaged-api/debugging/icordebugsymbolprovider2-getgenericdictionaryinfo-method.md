---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
ms.openlocfilehash: a6c32b72c5924399aeb13d56ddf9242fe7990f35
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379320"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a><span data-ttu-id="6e5a6-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)</span><span class="sxs-lookup"><span data-stu-id="6e5a6-102">ICorDebugSymbolProvider2::GetGenericDictionaryInfo Method</span></span>

<span data-ttu-id="6e5a6-103">Recupera una asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-103">Retrieves a generic dictionary map.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e5a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e5a6-104">Syntax</span></span>

```cpp
HRESULT GetGenericDictionaryInfo(
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="6e5a6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6e5a6-105">Parameters</span></span>

`ppMemoryBuffer`\
<span data-ttu-id="6e5a6-106">enuncia Un puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene la asignación de diccionario genérico.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object containing the generic dictionary map.</span></span> <span data-ttu-id="6e5a6-107">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-107">See the Remarks section for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e5a6-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6e5a6-108">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="6e5a6-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-109">This method is available with .NET Native only.</span></span>

<span data-ttu-id="6e5a6-110">La asignación se compone de dos secciones de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="6e5a6-110">The map consists of two top-level sections:</span></span>

- <span data-ttu-id="6e5a6-111">Un [directorio](#Directory) que contiene las direcciones virtuales relativas (RVA) de todos los diccionarios incluidos en esta asignación.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-111">A [directory](#Directory) containing the relative virtual addresses (RVA) of all dictionaries included in this map.</span></span>

- <span data-ttu-id="6e5a6-112">[Montón](#Heap) alineado en bytes que contiene información sobre la creación de instancias de objetos.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-112">A byte-aligned [heap](#Heap) that contains object instantiation information.</span></span> <span data-ttu-id="6e5a6-113">Se inicia inmediatamente después de la última entrada de directorio.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-113">It starts immediately after the last directory entry.</span></span>

<a name="Directory"></a>

## <a name="the-directory"></a><span data-ttu-id="6e5a6-114">El directorio</span><span class="sxs-lookup"><span data-stu-id="6e5a6-114">The Directory</span></span>

<span data-ttu-id="6e5a6-115">Cada entrada del directorio hace referencia a un desplazamiento dentro del montón; es decir, es un desplazamiento relativo al inicio del montón.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-115">Each entry in the directory refers to an offset inside the heap; that is, it is an offset that is relative to the start of the heap.</span></span> <span data-ttu-id="6e5a6-116">El valor de las entradas individuales no es necesariamente único; varias entradas de directorio pueden apuntar al mismo desplazamiento en el montón.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-116">The value of individual entries is not necessarily unique; it is possible for multiple directory entries to point to the same offset in the heap.</span></span>

<span data-ttu-id="6e5a6-117">La parte del directorio de la asignación del diccionario genérico tiene la estructura siguiente:</span><span class="sxs-lookup"><span data-stu-id="6e5a6-117">The directory portion of the generic dictionary map has the following structure:</span></span>

- <span data-ttu-id="6e5a6-118">Los primeros cuatro bytes contienen el número de entradas del diccionario (es decir, el número de direcciones virtuales relativas en el diccionario).</span><span class="sxs-lookup"><span data-stu-id="6e5a6-118">The first 4 bytes contains the number of dictionary entries (that is, the number of relative virtual addresses in the dictionary).</span></span> <span data-ttu-id="6e5a6-119">Haremos referencia a este valor como *N*. Si se establece el bit alto, las entradas se ordenan por dirección virtual relativa en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-119">We will refer to this value as *N*. If the high bit is set, the entries are sorted by relative virtual address in ascending order.</span></span>

- <span data-ttu-id="6e5a6-120">Las *N* entradas de directorio siguen.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-120">The *N* directory entries follow.</span></span> <span data-ttu-id="6e5a6-121">Cada entrada consta de 8 bytes, en dos segmentos de 4 bytes:</span><span class="sxs-lookup"><span data-stu-id="6e5a6-121">Each entry consists of 8 bytes, in two 4-byte segments:</span></span>

  - <span data-ttu-id="6e5a6-122">Bytes de 0 a 3: RVA; dirección virtual relativa del diccionario.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-122">Bytes 0-3: RVA; the dictionary's relative virtual address.</span></span>

  - <span data-ttu-id="6e5a6-123">Bytes de 4 a 7: desplazamiento; un desplazamiento relativo al inicio del montón.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-123">Bytes 4-7: Offset; an offset relative to the start of the heap.</span></span>

<a name="Heap"></a>

## <a name="the-heap"></a><span data-ttu-id="6e5a6-124">El montón</span><span class="sxs-lookup"><span data-stu-id="6e5a6-124">The Heap</span></span>

<span data-ttu-id="6e5a6-125">El tamaño del montón se puede calcular con un lector de secuencias restando la longitud de la secuencia del tamaño del directorio + 4.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-125">The heap’s size can be computed by a stream reader by subtracting the length of the stream from the directory size + 4.</span></span> <span data-ttu-id="6e5a6-126">En otras palabras:</span><span class="sxs-lookup"><span data-stu-id="6e5a6-126">In other words:</span></span>

```csharp
Heap Size = Stream.Length – (Directory Size + 4)
```

<span data-ttu-id="6e5a6-127">donde el tamaño del directorio es `N * 8`.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-127">where the directory size is `N * 8`.</span></span>

<span data-ttu-id="6e5a6-128">El formato de cada elemento de información sobre la creación de instancias en el montón es:</span><span class="sxs-lookup"><span data-stu-id="6e5a6-128">The format for each instantiation information item on the heap is:</span></span>

- <span data-ttu-id="6e5a6-129">La longitud de este elemento de información sobre la creación de instancias en bytes, en el formato de metadatos ECMA comprimido.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-129">The length of this instantiation information item in bytes in compressed ECMA metadata format.</span></span> <span data-ttu-id="6e5a6-130">El valor excluye esta información de longitud.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-130">The value excludes this length information.</span></span>

- <span data-ttu-id="6e5a6-131">El número de tipos de creación de instancias genéricos, o *T*, en formato de metadatos ECMA comprimido.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-131">The number of generic instantiation types, or *T*, in compressed ECMA metadata format.</span></span>

- <span data-ttu-id="6e5a6-132">Tipos *T* , cada uno representado en el formato de firma de tipo ECMA.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-132">*T* types, each represented in ECMA type signature format.</span></span>

<span data-ttu-id="6e5a6-133">Incluir la longitud de cada elemento del montón permite la ordenación simple de la sección del directorio sin afectar al montón.</span><span class="sxs-lookup"><span data-stu-id="6e5a6-133">The inclusion of the length for each heap element enables simple sorting of the directory section without affecting the heap.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e5a6-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e5a6-134">Requirements</span></span>

<span data-ttu-id="6e5a6-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e5a6-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6e5a6-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e5a6-136">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="6e5a6-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e5a6-137">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6e5a6-138">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e5a6-138">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6e5a6-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e5a6-139">See also</span></span>

- [<span data-ttu-id="6e5a6-140">Interfaz ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="6e5a6-140">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="6e5a6-141">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6e5a6-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
