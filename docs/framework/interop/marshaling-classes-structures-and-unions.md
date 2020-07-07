---
title: Calcular las referencias de clases, estructuras y uniones
description: Revise cómo serializar las referencias de clases, estructuras y uniones. Vea ejemplos de clases de serialización, estructuras con estructuras anidadas, matrices de estructuras y uniones.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
ms.openlocfilehash: 5e616b5bb513939cadd8fe5c72675ba0b6e070a3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621527"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="9bb84-104">Calcular las referencias de clases, estructuras y uniones</span><span class="sxs-lookup"><span data-stu-id="9bb84-104">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="9bb84-105">Las clases y las estructuras son similares en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bb84-105">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="9bb84-106">Ambas pueden tener campos, propiedades y eventos,</span><span class="sxs-lookup"><span data-stu-id="9bb84-106">Both can have fields, properties, and events.</span></span> <span data-ttu-id="9bb84-107">además de métodos estáticos y no estáticos.</span><span class="sxs-lookup"><span data-stu-id="9bb84-107">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="9bb84-108">Una diferencia importante entre ellas es que las estructuras son tipos de valor y las clases son tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="9bb84-108">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="9bb84-109">En la tabla siguiente se enumeran las opciones de serialización para clases, estructuras y uniones, se describe su uso y se proporciona un vínculo al ejemplo de invocación de la plataforma correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9bb84-109">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="9bb84-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="9bb84-110">Type</span></span>|<span data-ttu-id="9bb84-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bb84-111">Description</span></span>|<span data-ttu-id="9bb84-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bb84-112">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="9bb84-113">Clase por valor.</span><span class="sxs-lookup"><span data-stu-id="9bb84-113">Class by value.</span></span>|<span data-ttu-id="9bb84-114">Pasa una clase con miembros de tipo entero como un parámetro In/Out, al igual que el caso administrado.</span><span class="sxs-lookup"><span data-stu-id="9bb84-114">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="9bb84-115">Ejemplo SysTime</span><span class="sxs-lookup"><span data-stu-id="9bb84-115">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="9bb84-116">Estructura por valor.</span><span class="sxs-lookup"><span data-stu-id="9bb84-116">Structure by value.</span></span>|<span data-ttu-id="9bb84-117">Pasa las estructuras como parámetros In.</span><span class="sxs-lookup"><span data-stu-id="9bb84-117">Passes structures as In parameters.</span></span>|[<span data-ttu-id="9bb84-118">Ejemplo Structs</span><span class="sxs-lookup"><span data-stu-id="9bb84-118">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="9bb84-119">Estructura por referencia.</span><span class="sxs-lookup"><span data-stu-id="9bb84-119">Structure by reference.</span></span>|<span data-ttu-id="9bb84-120">Pasa estructuras como parámetros In/Out.</span><span class="sxs-lookup"><span data-stu-id="9bb84-120">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="9bb84-121">[Ejemplo OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9bb84-121">[OSInfo sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="9bb84-122">Estructura con estructuras anidadas (simplificada).</span><span class="sxs-lookup"><span data-stu-id="9bb84-122">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="9bb84-123">Pasa una clase que representa una estructura con estructuras anidadas en la función no administrada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-123">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="9bb84-124">La estructura se simplifica en una gran estructura en el prototipo administrado.</span><span class="sxs-lookup"><span data-stu-id="9bb84-124">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="9bb84-125">Ejemplo FindFile</span><span class="sxs-lookup"><span data-stu-id="9bb84-125">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="9bb84-126">Estructura con un puntero a otra estructura.</span><span class="sxs-lookup"><span data-stu-id="9bb84-126">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="9bb84-127">Pasa una estructura que contiene un puntero a una segunda estructura como miembro.</span><span class="sxs-lookup"><span data-stu-id="9bb84-127">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="9bb84-128">Ejemplo Structs</span><span class="sxs-lookup"><span data-stu-id="9bb84-128">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="9bb84-129">Matriz de estructuras con enteros por valor.</span><span class="sxs-lookup"><span data-stu-id="9bb84-129">Array of structures with integers by value.</span></span>|<span data-ttu-id="9bb84-130">Pasa una matriz de estructuras que solo contienen enteros como un parámetro In/Out.</span><span class="sxs-lookup"><span data-stu-id="9bb84-130">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="9bb84-131">Los miembros de la matriz se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="9bb84-131">Members of the array can be changed.</span></span>|[<span data-ttu-id="9bb84-132">Ejemplo Arrays</span><span class="sxs-lookup"><span data-stu-id="9bb84-132">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="9bb84-133">Matriz de estructuras con enteros y cadenas por referencia.</span><span class="sxs-lookup"><span data-stu-id="9bb84-133">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="9bb84-134">Pasa una matriz de estructuras que contienen enteros y cadenas como un parámetro Out.</span><span class="sxs-lookup"><span data-stu-id="9bb84-134">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="9bb84-135">La función llamada asigna memoria para la matriz.</span><span class="sxs-lookup"><span data-stu-id="9bb84-135">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="9bb84-136">Ejemplo OutArrayOfStructs</span><span class="sxs-lookup"><span data-stu-id="9bb84-136">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="9bb84-137">Uniones con tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="9bb84-137">Unions with value types.</span></span>|<span data-ttu-id="9bb84-138">Pasa uniones con tipos de valor (entero y doble).</span><span class="sxs-lookup"><span data-stu-id="9bb84-138">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="9bb84-139">Ejemplo Unions</span><span class="sxs-lookup"><span data-stu-id="9bb84-139">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="9bb84-140">Uniones con tipos mixtos.</span><span class="sxs-lookup"><span data-stu-id="9bb84-140">Unions with mixed types.</span></span>|<span data-ttu-id="9bb84-141">Pasa uniones con tipos mixtos (entero y cadena).</span><span class="sxs-lookup"><span data-stu-id="9bb84-141">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="9bb84-142">Ejemplo Unions</span><span class="sxs-lookup"><span data-stu-id="9bb84-142">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="9bb84-143">Struct con diseño específico de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="9bb84-143">Struct with platform-specific layout.</span></span>|<span data-ttu-id="9bb84-144">Pasa un tipo con definiciones de empaquetado nativo.</span><span class="sxs-lookup"><span data-stu-id="9bb84-144">Passes a type with native-packing definitions.</span></span>|[<span data-ttu-id="9bb84-145">Ejemplo de plataforma</span><span class="sxs-lookup"><span data-stu-id="9bb84-145">Platform sample</span></span>](#platform-sample)|
|<span data-ttu-id="9bb84-146">Valores NULL en la estructura.</span><span class="sxs-lookup"><span data-stu-id="9bb84-146">Null values in structure.</span></span>|<span data-ttu-id="9bb84-147">Pasa una referencia nula (**Nothing** en Visual Basic) en lugar de una referencia a un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="9bb84-147">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="9bb84-148">[Ejemplo HandleRef](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9bb84-148">[HandleRef sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="9bb84-149">Ejemplo Structs</span><span class="sxs-lookup"><span data-stu-id="9bb84-149">Structures sample</span></span>

<span data-ttu-id="9bb84-150">En este ejemplo se muestra cómo pasar una estructura que apunta a una segunda estructura, cómo pasar una estructura con otra estructura insertada y cómo pasar una estructura con una matriz insertada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-150">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="9bb84-151">En el ejemplo Structs se usan las siguientes funciones no administradas, junto con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="9bb84-151">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="9bb84-152">**TestStructInStruct** se exporta desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="9bb84-152">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="9bb84-153">**TestStructInStruct3** se exporta desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="9bb84-153">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="9bb84-154">**TestArrayInStruct** se exporta desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="9bb84-154">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="9bb84-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) es una biblioteca personalizada y no administrada que contiene implementaciones para las funciones enumeradas anteriormente y cuatro estructuras: **MYPERSON**, **MYPERSON2**, **MYPERSON3** y **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="9bb84-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="9bb84-156">Estas estructuras contienen los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="9bb84-156">These structures contain the following elements:</span></span>

```cpp
typedef struct _MYPERSON
{
   char* first;
   char* last;
} MYPERSON, *LP_MYPERSON;

typedef struct _MYPERSON2
{
   MYPERSON* person;
   int age;
} MYPERSON2, *LP_MYPERSON2;

typedef struct _MYPERSON3
{
   MYPERSON person;
   int age;
} MYPERSON3;

typedef struct _MYARRAYSTRUCT
{
   bool flag;
   int vals[ 3 ];
} MYARRAYSTRUCT;
```

<span data-ttu-id="9bb84-157">Las estructuras administradas `MyPerson`, `MyPerson2`, `MyPerson3` y `MyArrayStruct` tienen las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="9bb84-157">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="9bb84-158">`MyPerson` contiene solo miembros de cadena.</span><span class="sxs-lookup"><span data-stu-id="9bb84-158">`MyPerson` contains only string members.</span></span> <span data-ttu-id="9bb84-159">El campo [CharSet](specifying-a-character-set.md) establece las cadenas en formato ANSI cuando se pasan a la función no administrada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-159">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="9bb84-160">`MyPerson2` contiene un **IntPtr** a la estructura `MyPerson`.</span><span class="sxs-lookup"><span data-stu-id="9bb84-160">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="9bb84-161">El tipo **IntPtr** reemplaza el puntero original a la estructura no administrada porque las aplicaciones de .NET Framework no usan punteros a menos que el código se marque como **unsafe**.</span><span class="sxs-lookup"><span data-stu-id="9bb84-161">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="9bb84-162">`MyPerson3` contiene `MyPerson` como una estructura insertada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-162">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="9bb84-163">Una estructura insertada en otra estructura se puede simplificar mediante la colocación de los elementos de la estructura insertada directamente en la estructura principal. También se puede dejar como estructura insertada, como se hace en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9bb84-163">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="9bb84-164">`MyArrayStruct` contiene una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="9bb84-164">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="9bb84-165">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> establece el valor de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> en **ByValArray**, que se usa para indicar el número de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="9bb84-165">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="9bb84-166">En todas las estructuras de este ejemplo, el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> se aplica para garantizar que los miembros se organizan secuencialmente en la memoria, en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="9bb84-166">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="9bb84-167">La clase `NativeMethods` contiene prototipos administrados para los métodos `TestStructInStruct`, `TestStructInStruct3` y `TestArrayInStruct` llamados por la clase `App`.</span><span class="sxs-lookup"><span data-stu-id="9bb84-167">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="9bb84-168">Cada prototipo declara un único parámetro, como sigue:</span><span class="sxs-lookup"><span data-stu-id="9bb84-168">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="9bb84-169">`TestStructInStruct` declara una referencia al tipo `MyPerson2` como su parámetro.</span><span class="sxs-lookup"><span data-stu-id="9bb84-169">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="9bb84-170">`TestStructInStruct3` declara el tipo `MyPerson3` como su parámetro y pasa el parámetro por valor.</span><span class="sxs-lookup"><span data-stu-id="9bb84-170">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="9bb84-171">`TestArrayInStruct` declara una referencia al tipo `MyArrayStruct` como su parámetro.</span><span class="sxs-lookup"><span data-stu-id="9bb84-171">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="9bb84-172">Las estructuras como argumentos para los métodos se pasan por valor a menos que el parámetro contenga la palabra clave **ref** (**ByRef** en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="9bb84-172">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="9bb84-173">Por ejemplo, el método `TestStructInStruct` pasa una referencia (el valor de una dirección) a un objeto de tipo `MyPerson2` a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="9bb84-173">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="9bb84-174">Para manipular la estructura a la que apunta `MyPerson2`, en el ejemplo se crea un búfer de un tamaño especificado y se devuelve su dirección mediante la combinación de los métodos <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> y <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9bb84-174">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="9bb84-175">A continuación, se copia el contenido de la estructura administrada en el búfer no administrado.</span><span class="sxs-lookup"><span data-stu-id="9bb84-175">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="9bb84-176">Por último, se usa el método <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> para calcular referencias de datos desde el búfer no administrado a un objeto administrado y el método <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> para liberar el bloque de memoria no administrada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-176">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="9bb84-177">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="9bb84-177">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="9bb84-178">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="9bb84-178">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="9bb84-179">FindFile (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="9bb84-179">FindFile sample</span></span>

<span data-ttu-id="9bb84-180">En este ejemplo se muestra cómo pasar una estructura que contiene una segunda estructura insertada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-180">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="9bb84-181">También se muestra cómo usar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> para declarar una matriz de longitud fija dentro de la estructura.</span><span class="sxs-lookup"><span data-stu-id="9bb84-181">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="9bb84-182">En este ejemplo, los elementos de la estructura insertada se agregan a la estructura primaria.</span><span class="sxs-lookup"><span data-stu-id="9bb84-182">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="9bb84-183">Para obtener un ejemplo de una estructura insertada que no esté simplificada, vea [Ejemplo Structs](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9bb84-183">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="9bb84-184">En el ejemplo FindFile se usa la siguiente función no administrada, que se muestra con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="9bb84-184">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="9bb84-185">**FindFirstFile** exportada desde Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="9bb84-185">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="9bb84-186">La estructura original pasada a la función contiene los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9bb84-186">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _WIN32_FIND_DATA
{
  DWORD    dwFileAttributes;
  FILETIME ftCreationTime;
  FILETIME ftLastAccessTime;
  FILETIME ftLastWriteTime;
  DWORD    nFileSizeHigh;
  DWORD    nFileSizeLow;
  DWORD    dwReserved0;
  DWORD    dwReserved1;
  TCHAR    cFileName[ MAX_PATH ];
  TCHAR    cAlternateFileName[ 14 ];
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;
```

<span data-ttu-id="9bb84-187">En este ejemplo, la clase `FindData` contiene un miembro de datos correspondiente para cada elemento de la estructura original y de la estructura insertada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-187">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="9bb84-188">En lugar de dos búferes de caracteres originales, la clase sustituye cadenas.</span><span class="sxs-lookup"><span data-stu-id="9bb84-188">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="9bb84-189">**MarshalAsAttribute** establece el valor de la enumeración <xref:System.Runtime.InteropServices.UnmanagedType> en **ByValTStr**, que se usa para identificar las matrices de caracteres de longitud fija insertadas que aparecen en las estructuras no administradas.</span><span class="sxs-lookup"><span data-stu-id="9bb84-189">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="9bb84-190">La clase `NativeMethods` contiene un prototipo administrado del método `FindFirstFile`, que pasa la clase `FindData` como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="9bb84-190">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="9bb84-191">El parámetro se debe declarar con los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> porque las clases, que son tipos de referencia, se pasan como parámetros In de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-191">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="9bb84-192">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="9bb84-192">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="9bb84-193">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="9bb84-193">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="9bb84-194">Unions (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="9bb84-194">Unions sample</span></span>

<span data-ttu-id="9bb84-195">En este ejemplo se muestra cómo pasar estructuras que solo contienen tipos de valor y estructuras que contienen un tipo de valor y una cadena como parámetros para una función no administrada que espera recibir una unión.</span><span class="sxs-lookup"><span data-stu-id="9bb84-195">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="9bb84-196">Una unión representa una ubicación de memoria que puede ser compartida por dos o más variables.</span><span class="sxs-lookup"><span data-stu-id="9bb84-196">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="9bb84-197">En el ejemplo Unions se usa la siguiente función no administrada, que se muestra con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="9bb84-197">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="9bb84-198">**TestUnion** exportada desde PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="9bb84-198">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="9bb84-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) es una biblioteca personalizada no administrada que contiene una implementación para la función enumerada anteriormente y dos uniones, **MYUNION** y **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="9bb84-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="9bb84-200">Las uniones contienen los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="9bb84-200">The unions contain the following elements:</span></span>

```cpp
union MYUNION
{
    int number;
    double d;
}

union MYUNION2
{
    int i;
    char str[128];
};
```

<span data-ttu-id="9bb84-201">En código administrado, las uniones se definen como estructuras.</span><span class="sxs-lookup"><span data-stu-id="9bb84-201">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="9bb84-202">La estructura `MyUnion` contiene dos tipos de valor como miembros: un entero y un doble.</span><span class="sxs-lookup"><span data-stu-id="9bb84-202">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="9bb84-203">El atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> está establecido para controlar la posición exacta de cada miembro de datos.</span><span class="sxs-lookup"><span data-stu-id="9bb84-203">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="9bb84-204">El atributo <xref:System.Runtime.InteropServices.FieldOffsetAttribute> proporciona la posición física de los campos dentro de la representación no administrada de una unión.</span><span class="sxs-lookup"><span data-stu-id="9bb84-204">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="9bb84-205">Observe que ambos miembros tienen los mismos valores de desplazamiento, por lo que pueden definir la misma parte de memoria.</span><span class="sxs-lookup"><span data-stu-id="9bb84-205">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="9bb84-206">`MyUnion2_1` y `MyUnion2_2` contienen un tipo de valor (entero) y una cadena, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9bb84-206">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="9bb84-207">En código administrado, los tipos de valor y los tipos de referencia no pueden superponerse.</span><span class="sxs-lookup"><span data-stu-id="9bb84-207">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="9bb84-208">En este ejemplo se usa la sobrecarga de métodos para permitir que el llamador utilice ambos tipos cuando llama a la misma función no administrada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-208">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="9bb84-209">El diseño de `MyUnion2_1` es explícito y tiene un valor de desplazamiento preciso.</span><span class="sxs-lookup"><span data-stu-id="9bb84-209">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="9bb84-210">Por el contrario, `MyUnion2_2` tiene un diseño secuencial porque no se permiten diseños explícitos con tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="9bb84-210">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="9bb84-211">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> establece el valor de la enumeración <xref:System.Runtime.InteropServices.UnmanagedType> en **ByValTStr**, que se usa para identificar las matrices de caracteres de longitud fija insertadas que aparecen en la representación no administrada de la unión.</span><span class="sxs-lookup"><span data-stu-id="9bb84-211">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="9bb84-212">La clase `NativeMethods` contiene los prototipos para los métodos `TestUnion` y `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="9bb84-212">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="9bb84-213">`TestUnion2` se sobrecarga para declarar `MyUnion2_1` o `MyUnion2_2` como parámetros.</span><span class="sxs-lookup"><span data-stu-id="9bb84-213">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="9bb84-214">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="9bb84-214">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="9bb84-215">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="9bb84-215">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="platform-sample"></a><span data-ttu-id="9bb84-216">Ejemplo de plataforma</span><span class="sxs-lookup"><span data-stu-id="9bb84-216">Platform sample</span></span>

<span data-ttu-id="9bb84-217">En algunos escenarios, los diseños de `struct` y `union` pueden variar en función de la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="9bb84-217">In some scenarios, `struct` and `union` layouts can differ depending on the targeted platform.</span></span> <span data-ttu-id="9bb84-218">Por ejemplo, considere la definición del tipo [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) en un escenario COM:</span><span class="sxs-lookup"><span data-stu-id="9bb84-218">For example, consider the [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) type when defined in a COM scenario:</span></span>

```c++
#include <pshpack8.h> /* Defines the packing of the struct */
typedef struct _STRRET
    {
    UINT uType;
    /* [switch_is][switch_type] */ union
        {
        /* [case()][string] */ LPWSTR pOleStr;
        /* [case()] */ UINT uOffset;
        /* [case()] */ char cStr[ 260 ];
        }  DUMMYUNIONNAME;
    }  STRRET;
#include <poppack.h>
```

<span data-ttu-id="9bb84-219">El `struct` anterior se declara con los encabezados de Windows que influyen en el diseño de memoria del tipo.</span><span class="sxs-lookup"><span data-stu-id="9bb84-219">The above `struct` is declared with Windows' headers that influence the memory layout of the type.</span></span> <span data-ttu-id="9bb84-220">Cuando se definen en un entorno administrado, estos detalles de diseño son necesarios para interoperar correctamente con código nativo.</span><span class="sxs-lookup"><span data-stu-id="9bb84-220">When defined in a managed environment, these layout details are needed to properly interoperate with native code.</span></span>

<span data-ttu-id="9bb84-221">La definición administrada correcta de este tipo en un proceso de 32 bits es:</span><span class="sxs-lookup"><span data-stu-id="9bb84-221">The correct managed definition of this type in a 32-bit process is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 264)]
public struct STRRET_32
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(4)]
    public IntPtr pOleStr;

    [FieldOffset(4)]
    public uint uOffset;

    [FieldOffset(4)]
    public IntPtr cStr;
}
```

<span data-ttu-id="9bb84-222">En un proceso de 64 bits, el tamaño *y* los desplazamientos de los campos son diferentes.</span><span class="sxs-lookup"><span data-stu-id="9bb84-222">On a 64-bit process, the size *and* field offsets are different.</span></span> <span data-ttu-id="9bb84-223">El diseño correcto es:</span><span class="sxs-lookup"><span data-stu-id="9bb84-223">The correct layout is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 272)]
public struct STRRET_64
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(8)]
    public IntPtr pOleStr;

    [FieldOffset(8)]
    public uint uOffset;

    [FieldOffset(8)]
    public IntPtr cStr;
}
```

<span data-ttu-id="9bb84-224">Si no se considera correctamente el diseño nativo en un escenario de interoperabilidad, pueden producirse bloqueos aleatorios o, aún peor, cálculos incorrectos.</span><span class="sxs-lookup"><span data-stu-id="9bb84-224">Failure to properly consider the native layout in an interop scenario can result in random crashes or worse, incorrect computations.</span></span>

<span data-ttu-id="9bb84-225">De forma predeterminada, los ensamblados de .NET se pueden ejecutar tanto en las versiones de 32 bits como en las de 64 bits del runtime de .NET.</span><span class="sxs-lookup"><span data-stu-id="9bb84-225">By default, .NET assemblies can run in both a 32-bit and 64-bit version of the .NET runtime.</span></span> <span data-ttu-id="9bb84-226">La aplicación debe esperar hasta el tiempo de ejecución para decidir qué definiciones anteriores usar.</span><span class="sxs-lookup"><span data-stu-id="9bb84-226">The app must wait until run time to decide which of the previous definitions to use.</span></span>

<span data-ttu-id="9bb84-227">El fragmento de código siguiente es un ejemplo de cómo elegir entre las definiciones de 32 bits y 64 bits en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9bb84-227">The following code snippet shows an example of how to choose between the 32-bit and 64-bit definition at run time.</span></span>

```CSharp
if (IntPtr.Size == 8)
{
    // Use the STRRET_64 definition
}
else
{
    Debug.Assert(IntPtr.Size == 4);
    // Use the STRRET_32 definition
}
```

## <a name="systime-sample"></a><span data-ttu-id="9bb84-228">SysTime (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="9bb84-228">SysTime sample</span></span>

<span data-ttu-id="9bb84-229">En este ejemplo se muestra cómo pasar un puntero a una clase a una función no administrada que espera recibir un puntero a una estructura.</span><span class="sxs-lookup"><span data-stu-id="9bb84-229">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="9bb84-230">En el ejemplo SysTime se usa la siguiente función no administrada, que se muestra con su declaración de función original:</span><span class="sxs-lookup"><span data-stu-id="9bb84-230">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="9bb84-231">**GetSystemTime** exportada desde Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="9bb84-231">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="9bb84-232">La estructura original pasada a la función contiene los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9bb84-232">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="9bb84-233">En este ejemplo, la clase `SystemTime` contiene los elementos de la estructura original representados como miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="9bb84-233">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="9bb84-234">El atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> se establece para garantizar que los miembros se organizan secuencialmente en la memoria, en el orden en que aparecen.</span><span class="sxs-lookup"><span data-stu-id="9bb84-234">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="9bb84-235">La clase `NativeMethods` contiene un prototipo administrado del método `GetSystemTime`, que pasa la clase `SystemTime` como un parámetro In/Out de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-235">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="9bb84-236">El parámetro se debe declarar con los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> porque las clases, que son tipos de referencia, se pasan como parámetros In de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-236">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="9bb84-237">Para que el autor de la llamada reciba los resultados, deben aplicarse explícitamente estos [atributos direccionales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9bb84-237">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="9bb84-238">La clase `App` crea una nueva instancia de la clase `SystemTime` y tiene acceso a sus campos de datos.</span><span class="sxs-lookup"><span data-stu-id="9bb84-238">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="9bb84-239">Ejemplos de código</span><span class="sxs-lookup"><span data-stu-id="9bb84-239">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="9bb84-240">OutArrayOfStructs (ejemplo)</span><span class="sxs-lookup"><span data-stu-id="9bb84-240">OutArrayOfStructs sample</span></span>

<span data-ttu-id="9bb84-241">En este ejemplo se muestra cómo pasar una matriz de estructuras que contiene enteros y cadenas como parámetros Out a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="9bb84-241">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="9bb84-242">En el ejemplo se muestra cómo llamar a una función nativa mediante la clase <xref:System.Runtime.InteropServices.Marshal> y código no seguro.</span><span class="sxs-lookup"><span data-stu-id="9bb84-242">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="9bb84-243">En este ejemplo se usan funciones de contenedor e invocaciones de plataforma definidas en [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), que también se proporciona en los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="9bb84-243">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="9bb84-244">Se usa la función `TestOutArrayOfStructs` y la estructura `MYSTRSTRUCT2`.</span><span class="sxs-lookup"><span data-stu-id="9bb84-244">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="9bb84-245">La estructura contiene los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="9bb84-245">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="9bb84-246">La clase `MyStruct` contiene un objeto de cadena de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="9bb84-246">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="9bb84-247">El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> especifica el formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="9bb84-247">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="9bb84-248">`MyUnsafeStruct` es una estructura que contiene un tipo <xref:System.IntPtr> en lugar de una cadena.</span><span class="sxs-lookup"><span data-stu-id="9bb84-248">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="9bb84-249">La clase `NativeMethods` contiene el método de prototipo `TestOutArrayOfStructs` sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="9bb84-249">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="9bb84-250">Si un método declara un puntero como parámetro, la clase se debe marcar con la palabra clave `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="9bb84-250">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="9bb84-251">Puesto que Visual Basic no puede utilizar código no seguro, el método sobrecargado, el modificado unsafe y la estructura `MyUnsafeStruct` no son innecesarios.</span><span class="sxs-lookup"><span data-stu-id="9bb84-251">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="9bb84-252">La clase `App` implementa el método `UsingMarshaling`, que realiza todas las tareas necesarias para pasar la matriz.</span><span class="sxs-lookup"><span data-stu-id="9bb84-252">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="9bb84-253">La matriz se marca con la palabra clave `out` (`ByRef` en Visual Basic) para indicar que los datos se pasan del destinatario al llamador.</span><span class="sxs-lookup"><span data-stu-id="9bb84-253">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="9bb84-254">La implementación usa los siguientes métodos de la clase <xref:System.Runtime.InteropServices.Marshal>:</span><span class="sxs-lookup"><span data-stu-id="9bb84-254">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="9bb84-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> para calcular las referencias de datos desde el búfer no administrado a un objeto administrado.</span><span class="sxs-lookup"><span data-stu-id="9bb84-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="9bb84-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> para liberar la memoria reservada para las cadenas en la estructura.</span><span class="sxs-lookup"><span data-stu-id="9bb84-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="9bb84-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> para liberar la memoria reservada para la matriz.</span><span class="sxs-lookup"><span data-stu-id="9bb84-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="9bb84-258">Como se mencionó anteriormente, C# permite código no seguro y Visual Basic, no.</span><span class="sxs-lookup"><span data-stu-id="9bb84-258">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="9bb84-259">En el ejemplo de C#, `UsingUnsafePointer` es una implementación de método alternativo que usa punteros en lugar de la clase <xref:System.Runtime.InteropServices.Marshal> para devolver la matriz que contiene la estructura `MyUnsafeStruct`.</span><span class="sxs-lookup"><span data-stu-id="9bb84-259">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="9bb84-260">Declaración de prototipos</span><span class="sxs-lookup"><span data-stu-id="9bb84-260">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="9bb84-261">Llamadas a funciones</span><span class="sxs-lookup"><span data-stu-id="9bb84-261">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="9bb84-262">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bb84-262">See also</span></span>

- [<span data-ttu-id="9bb84-263">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="9bb84-263">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="9bb84-264">Serialización de cadenas</span><span class="sxs-lookup"><span data-stu-id="9bb84-264">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="9bb84-265">Serialización de tipos diferentes de matrices</span><span class="sxs-lookup"><span data-stu-id="9bb84-265">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)
