---
title: Cálculo de referencias de tipos diferentes de matrices
description: Serialice los distintos tipos de matriz, como enteros por valor o referencia, enteros de dos dimensiones por valor, cadenas por valor y estructuras con enteros o cadenas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
ms.openlocfilehash: b7777e99daf9d294bf26033f470a6e562b7b727f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269098"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="51494-103">Cálculo de referencias de tipos diferentes de matrices</span><span class="sxs-lookup"><span data-stu-id="51494-103">Marshaling Different Types of Arrays</span></span>

<span data-ttu-id="51494-104">Una matriz es un tipo de referencia en código administrado que contiene uno o varios elementos del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="51494-104">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="51494-105">Aunque las matrices son tipos de referencia, se pasan como parámetros In a funciones no administradas.</span><span class="sxs-lookup"><span data-stu-id="51494-105">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="51494-106">Este comportamiento no se corresponde con la manera en que se pasan las matrices administradas a los objetos administrados, que es como parámetros In/Out.</span><span class="sxs-lookup"><span data-stu-id="51494-106">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="51494-107">Para obtener más información, consulte [Copiar y fijar](copying-and-pinning.md).</span><span class="sxs-lookup"><span data-stu-id="51494-107">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="51494-108">En la tabla siguiente se muestran las opciones de cálculo de referencias de matrices y se describe su uso.</span><span class="sxs-lookup"><span data-stu-id="51494-108">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="51494-109">Matriz</span><span class="sxs-lookup"><span data-stu-id="51494-109">Array</span></span>|<span data-ttu-id="51494-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="51494-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51494-111">De enteros por valor.</span><span class="sxs-lookup"><span data-stu-id="51494-111">Of integers by value.</span></span>|<span data-ttu-id="51494-112">Pasa una matriz de enteros como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="51494-112">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="51494-113">De enteros por referencia.</span><span class="sxs-lookup"><span data-stu-id="51494-113">Of integers by reference.</span></span>|<span data-ttu-id="51494-114">Pasa una matriz de enteros como un parámetro In/Out.</span><span class="sxs-lookup"><span data-stu-id="51494-114">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="51494-115">De enteros por valor (bidimensional).</span><span class="sxs-lookup"><span data-stu-id="51494-115">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="51494-116">Pasa una matriz multidimensional de enteros como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="51494-116">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="51494-117">De cadenas por valor.</span><span class="sxs-lookup"><span data-stu-id="51494-117">Of strings by value.</span></span>|<span data-ttu-id="51494-118">Pasa una matriz de cadenas como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="51494-118">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="51494-119">De estructuras con enteros.</span><span class="sxs-lookup"><span data-stu-id="51494-119">Of structures with integers.</span></span>|<span data-ttu-id="51494-120">Pasa una matriz de estructuras que contienen enteros como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="51494-120">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="51494-121">De estructuras con cadenas.</span><span class="sxs-lookup"><span data-stu-id="51494-121">Of structures with strings.</span></span>|<span data-ttu-id="51494-122">Pasa una matriz de estructuras que solo contienen cadenas como un parámetro In/Out.</span><span class="sxs-lookup"><span data-stu-id="51494-122">Passes an array of structures that contain only strings as an In/Out parameter.</span></span> <span data-ttu-id="51494-123">Los miembros de la matriz se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="51494-123">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="51494-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51494-124">Example</span></span>  

 <span data-ttu-id="51494-125">En este ejemplo se muestra cómo pasar los siguientes tipos de matrices:</span><span class="sxs-lookup"><span data-stu-id="51494-125">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
- <span data-ttu-id="51494-126">Matriz de enteros por valor.</span><span class="sxs-lookup"><span data-stu-id="51494-126">Array of integers by value.</span></span>  
  
- <span data-ttu-id="51494-127">Matriz de enteros por referencia, que se puede cambiar de tamaño.</span><span class="sxs-lookup"><span data-stu-id="51494-127">Array of integers by reference, which can be resized.</span></span>  
  
- <span data-ttu-id="51494-128">Matriz multidimensional de enteros por valor.</span><span class="sxs-lookup"><span data-stu-id="51494-128">Multidimensional array (matrix) of integers by value.</span></span>  
  
- <span data-ttu-id="51494-129">Matriz de cadenas por valor.</span><span class="sxs-lookup"><span data-stu-id="51494-129">Array of strings by value.</span></span>  
  
- <span data-ttu-id="51494-130">Matriz de estructuras con enteros.</span><span class="sxs-lookup"><span data-stu-id="51494-130">Array of structures with integers.</span></span>  
  
- <span data-ttu-id="51494-131">Matriz de estructuras con cadenas.</span><span class="sxs-lookup"><span data-stu-id="51494-131">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="51494-132">A menos que una matriz se calcule explícitamente por referencia, el comportamiento predeterminado calcula las referencias de la matriz como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="51494-132">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="51494-133">Puede cambiar este comportamiento aplicando explícitamente los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="51494-133">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="51494-134">En el ejemplo Arrays se usan las siguientes funciones no administradas, que se muestran con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="51494-134">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
- <span data-ttu-id="51494-135">**TestArrayOfInts** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="51494-135">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- <span data-ttu-id="51494-136">**TestRefArrayOfInts** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="51494-136">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- <span data-ttu-id="51494-137">**TestMatrixOfInts** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="51494-137">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- <span data-ttu-id="51494-138">**TestArrayOfStrings** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="51494-138">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- <span data-ttu-id="51494-139">**TestArrayOfStructs** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="51494-139">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- <span data-ttu-id="51494-140">**TestArrayOfStructs2** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="51494-140">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="51494-141">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) es una biblioteca personalizada no administrada que contiene implementaciones de las funciones enumeradas anteriormente y dos variables de estructura: **MYSTRSTRUCT** y **MYSTRSTRUCT2**.</span><span class="sxs-lookup"><span data-stu-id="51494-141">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="51494-142">Estas estructuras contienen los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="51494-142">The structures contain the following elements:</span></span>  
  
```cpp
typedef struct _MYPOINT  
{  
   int x;
   int y;
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;
   char* last;
} MYPERSON;  
```  
  
 <span data-ttu-id="51494-143">En este ejemplo, las estructuras `MyPoint` y `MyPerson` contienen tipos insertados.</span><span class="sxs-lookup"><span data-stu-id="51494-143">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="51494-144">El atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> se establece para garantizar que los miembros se organizan secuencialmente en la memoria, en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="51494-144">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="51494-145">La clase `NativeMethods` contiene un conjunto de métodos llamados por la clase `App` .</span><span class="sxs-lookup"><span data-stu-id="51494-145">The `NativeMethods` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="51494-146">Para obtener detalles específicos sobre cómo pasar matrices, consulte los comentarios del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="51494-146">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="51494-147">Una matriz, que es un tipo de referencia, se pasa como un parámetro In de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="51494-147">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="51494-148">Para que el llamador reciba los resultados, se deben aplicar **InAttribute** y **OutAttribute** de manera explícita al argumento que contiene la matriz.</span><span class="sxs-lookup"><span data-stu-id="51494-148">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="51494-149">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="51494-149">Declaring Prototypes</span></span>  

 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="51494-150">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="51494-150">Calling Functions</span></span>  

 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="51494-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="51494-151">See also</span></span>

- [<span data-ttu-id="51494-152">Tipos de datos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="51494-152">Platform invoke data types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="51494-153">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="51494-153">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
