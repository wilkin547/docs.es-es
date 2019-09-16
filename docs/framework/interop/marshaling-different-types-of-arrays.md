---
title: Cálculo de referencias de tipos diferentes de matrices
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 358c7f1a339fd473271574a4e97e201f5c15f871
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894169"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="27d61-102">Cálculo de referencias de tipos diferentes de matrices</span><span class="sxs-lookup"><span data-stu-id="27d61-102">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="27d61-103">Una matriz es un tipo de referencia en código administrado que contiene uno o varios elementos del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="27d61-103">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="27d61-104">Aunque las matrices son tipos de referencia, se pasan como parámetros In a funciones no administradas.</span><span class="sxs-lookup"><span data-stu-id="27d61-104">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="27d61-105">Este comportamiento no se corresponde con la manera en que se pasan las matrices administradas a los objetos administrados, que es como parámetros In/Out.</span><span class="sxs-lookup"><span data-stu-id="27d61-105">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="27d61-106">Para obtener más información, consulte [Copiar y fijar](copying-and-pinning.md).</span><span class="sxs-lookup"><span data-stu-id="27d61-106">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="27d61-107">En la tabla siguiente se muestran las opciones de cálculo de referencias de matrices y se describe su uso.</span><span class="sxs-lookup"><span data-stu-id="27d61-107">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="27d61-108">Matriz</span><span class="sxs-lookup"><span data-stu-id="27d61-108">Array</span></span>|<span data-ttu-id="27d61-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="27d61-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="27d61-110">De enteros por valor.</span><span class="sxs-lookup"><span data-stu-id="27d61-110">Of integers by value.</span></span>|<span data-ttu-id="27d61-111">Pasa una matriz de enteros como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="27d61-111">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="27d61-112">De enteros por referencia.</span><span class="sxs-lookup"><span data-stu-id="27d61-112">Of integers by reference.</span></span>|<span data-ttu-id="27d61-113">Pasa una matriz de enteros como un parámetro In/Out.</span><span class="sxs-lookup"><span data-stu-id="27d61-113">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="27d61-114">De enteros por valor (bidimensional).</span><span class="sxs-lookup"><span data-stu-id="27d61-114">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="27d61-115">Pasa una matriz multidimensional de enteros como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="27d61-115">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="27d61-116">De cadenas por valor.</span><span class="sxs-lookup"><span data-stu-id="27d61-116">Of strings by value.</span></span>|<span data-ttu-id="27d61-117">Pasa una matriz de cadenas como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="27d61-117">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="27d61-118">De estructuras con enteros.</span><span class="sxs-lookup"><span data-stu-id="27d61-118">Of structures with integers.</span></span>|<span data-ttu-id="27d61-119">Pasa una matriz de estructuras que contienen enteros como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="27d61-119">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="27d61-120">De estructuras con cadenas.</span><span class="sxs-lookup"><span data-stu-id="27d61-120">Of structures with strings.</span></span>|<span data-ttu-id="27d61-121">Pasa una matriz de estructuras que solo contienen cadenas como un parámetro In/Out.</span><span class="sxs-lookup"><span data-stu-id="27d61-121">Passes an array of structures that contain only strings as an In/Out parameter.</span></span> <span data-ttu-id="27d61-122">Los miembros de la matriz se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="27d61-122">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27d61-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27d61-123">Example</span></span>  
 <span data-ttu-id="27d61-124">En este ejemplo se muestra cómo pasar los siguientes tipos de matrices:</span><span class="sxs-lookup"><span data-stu-id="27d61-124">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
- <span data-ttu-id="27d61-125">Matriz de enteros por valor.</span><span class="sxs-lookup"><span data-stu-id="27d61-125">Array of integers by value.</span></span>  
  
- <span data-ttu-id="27d61-126">Matriz de enteros por referencia, que se puede cambiar de tamaño.</span><span class="sxs-lookup"><span data-stu-id="27d61-126">Array of integers by reference, which can be resized.</span></span>  
  
- <span data-ttu-id="27d61-127">Matriz multidimensional de enteros por valor.</span><span class="sxs-lookup"><span data-stu-id="27d61-127">Multidimensional array (matrix) of integers by value.</span></span>  
  
- <span data-ttu-id="27d61-128">Matriz de cadenas por valor.</span><span class="sxs-lookup"><span data-stu-id="27d61-128">Array of strings by value.</span></span>  
  
- <span data-ttu-id="27d61-129">Matriz de estructuras con enteros.</span><span class="sxs-lookup"><span data-stu-id="27d61-129">Array of structures with integers.</span></span>  
  
- <span data-ttu-id="27d61-130">Matriz de estructuras con cadenas.</span><span class="sxs-lookup"><span data-stu-id="27d61-130">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="27d61-131">A menos que una matriz se calcule explícitamente por referencia, el comportamiento predeterminado calcula las referencias de la matriz como un parámetro In.</span><span class="sxs-lookup"><span data-stu-id="27d61-131">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="27d61-132">Puede cambiar este comportamiento aplicando explícitamente los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="27d61-132">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="27d61-133">En el ejemplo Arrays se usan las siguientes funciones no administradas, que se muestran con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="27d61-133">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
- <span data-ttu-id="27d61-134">**TestArrayOfInts** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="27d61-134">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- <span data-ttu-id="27d61-135">**TestRefArrayOfInts** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="27d61-135">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- <span data-ttu-id="27d61-136">**TestMatrixOfInts** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="27d61-136">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- <span data-ttu-id="27d61-137">**TestArrayOfStrings** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="27d61-137">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- <span data-ttu-id="27d61-138">**TestArrayOfStructs** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="27d61-138">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- <span data-ttu-id="27d61-139">**TestArrayOfStructs2** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="27d61-139">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="27d61-140">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) es una biblioteca personalizada no administrada que contiene implementaciones de las funciones enumeradas anteriormente y dos variables de estructura: **MYSTRSTRUCT** y **MYSTRSTRUCT2**.</span><span class="sxs-lookup"><span data-stu-id="27d61-140">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="27d61-141">Estas estructuras contienen los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="27d61-141">The structures contain the following elements:</span></span>  
  
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
  
 <span data-ttu-id="27d61-142">En este ejemplo, las estructuras `MyPoint` y `MyPerson` contienen tipos insertados.</span><span class="sxs-lookup"><span data-stu-id="27d61-142">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="27d61-143">El atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> se establece para garantizar que los miembros se organizan secuencialmente en la memoria, en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="27d61-143">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="27d61-144">La clase `LibWrap` contiene un conjunto de métodos llamados por la clase `App` .</span><span class="sxs-lookup"><span data-stu-id="27d61-144">The `LibWrap` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="27d61-145">Para obtener detalles específicos sobre cómo pasar matrices, consulte los comentarios del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="27d61-145">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="27d61-146">Una matriz, que es un tipo de referencia, se pasa como un parámetro In de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="27d61-146">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="27d61-147">Para que el llamador reciba los resultados, se deben aplicar **InAttribute** y **OutAttribute** de manera explícita al argumento que contiene la matriz.</span><span class="sxs-lookup"><span data-stu-id="27d61-147">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="27d61-148">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="27d61-148">Declaring Prototypes</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="27d61-149">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="27d61-149">Calling Functions</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="27d61-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="27d61-150">See also</span></span>

- [<span data-ttu-id="27d61-151">Tipos de datos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="27d61-151">Platform invoke data types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="27d61-152">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="27d61-152">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
