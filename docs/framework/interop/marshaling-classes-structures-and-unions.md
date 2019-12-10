---
title: Calcular las referencias de clases, estructuras y uniones
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
ms.openlocfilehash: d761d8ed7488e99f29d4844d061867915a624b96
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960008"
---
# <a name="marshaling-classes-structures-and-unions"></a>Calcular las referencias de clases, estructuras y uniones

Las clases y las estructuras son similares en .NET Framework. Ambas pueden tener campos, propiedades y eventos, además de métodos estáticos y no estáticos. Una diferencia importante entre ellas es que las estructuras son tipos de valor y las clases son tipos de referencia.

En la tabla siguiente se enumeran las opciones de serialización para clases, estructuras y uniones, se describe su uso y se proporciona un vínculo al ejemplo de invocación de la plataforma correspondiente.

|Tipo de|Descripción|Ejemplo|
|----------|-----------------|------------|
|Clase por valor.|Pasa una clase con miembros de tipo entero como un parámetro In/Out, al igual que el caso administrado.|[Ejemplo de SysTime](#systime-sample)|
|Estructura por valor.|Pasa las estructuras como parámetros In.|[Ejemplo de estructuras](#structures-sample)|
|Estructura por referencia.|Pasa estructuras como parámetros In/Out.|[OSInfo (ejemplo)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))|
|Estructura con estructuras anidadas (simplificada).|Pasa una clase que representa una estructura con estructuras anidadas en la función no administrada. La estructura se simplifica en una gran estructura en el prototipo administrado.|[Ejemplo FindFile](#findfile-sample)|
|Estructura con un puntero a otra estructura.|Pasa una estructura que contiene un puntero a una segunda estructura como miembro.|[Ejemplo de estructuras](#structures-sample)|
|Matriz de estructuras con enteros por valor.|Pasa una matriz de estructuras que solo contienen enteros como un parámetro In/Out. Los miembros de la matriz se pueden cambiar.|[Ejemplo de matrices](marshaling-different-types-of-arrays.md)|
|Matriz de estructuras con enteros y cadenas por referencia.|Pasa una matriz de estructuras que contienen enteros y cadenas como un parámetro Out. La función llamada asigna memoria para la matriz.|[Ejemplo de OutArrayOfStructs](#outarrayofstructs-sample)|
|Uniones con tipos de valor.|Pasa uniones con tipos de valor (entero y doble).|[Ejemplo uniones](#unions-sample)|
|Uniones con tipos mixtos.|Pasa uniones con tipos mixtos (entero y cadena).|[Ejemplo uniones](#unions-sample)|
|Valores NULL en la estructura.|Pasa una referencia nula (**Nothing** en Visual Basic) en lugar de una referencia a un tipo de valor.|[Ejemplo de HandleRef](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))|

## <a name="structures-sample"></a>Ejemplo Structs

En este ejemplo se muestra cómo pasar una estructura que apunta a una segunda estructura, cómo pasar una estructura con otra estructura insertada y cómo pasar una estructura con una matriz insertada.  
  
En el ejemplo Structs se usan las siguientes funciones no administradas, junto con su declaración de función original:

- **TestStructInStruct** se exporta desde PinvokeLib.dll.

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- **TestStructInStruct3** se exporta desde PinvokeLib.dll.

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- **TestArrayInStruct** se exporta desde PinvokeLib.dll.

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) es una biblioteca personalizada y no administrada que contiene implementaciones para las funciones enumeradas anteriormente y cuatro estructuras: **MYPERSON**, **MYPERSON2**, **MYPERSON3** y **MYARRAYSTRUCT**. Estas estructuras contienen los siguientes elementos:

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

Las estructuras administradas `MyPerson`, `MyPerson2`, `MyPerson3` y `MyArrayStruct` tienen las características siguientes:

- `MyPerson` contiene solo miembros de cadena. El campo [CharSet](specifying-a-character-set.md) establece las cadenas en formato ANSI cuando se pasan a la función no administrada.

- `MyPerson2` contiene un **IntPtr** a la estructura `MyPerson`. El tipo **IntPtr** reemplaza el puntero original a la estructura no administrada porque las aplicaciones de .NET Framework no usan punteros a menos que el código se marque como **unsafe**.

- `MyPerson3` contiene `MyPerson` como una estructura insertada. Una estructura insertada en otra estructura se puede simplificar mediante la colocación de los elementos de la estructura insertada directamente en la estructura principal. También se puede dejar como estructura insertada, como se hace en este ejemplo.

- `MyArrayStruct` contiene una matriz de enteros. El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> establece el valor de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> en **ByValArray**, que se usa para indicar el número de elementos de la matriz.

En todas las estructuras de este ejemplo, el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> se aplica para garantizar que los miembros se organizan secuencialmente en la memoria, en el orden en que aparecen.

La clase `NativeMethods` contiene prototipos administrados para los métodos `TestStructInStruct`, `TestStructInStruct3` y `TestArrayInStruct` llamados por la clase `App`. Cada prototipo declara un único parámetro, como sigue:

- `TestStructInStruct` declara una referencia al tipo `MyPerson2` como su parámetro.

- `TestStructInStruct3` declara el tipo `MyPerson3` como su parámetro y pasa el parámetro por valor.

- `TestArrayInStruct` declara una referencia al tipo `MyArrayStruct` como su parámetro.

Las estructuras como argumentos para los métodos se pasan por valor a menos que el parámetro contenga la palabra clave **ref** (**ByRef** en Visual Basic). Por ejemplo, el método `TestStructInStruct` pasa una referencia (el valor de una dirección) a un objeto de tipo `MyPerson2` a código no administrado. Para manipular la estructura a la que apunta `MyPerson2`, en el ejemplo se crea un búfer de un tamaño especificado y se devuelve su dirección mediante la combinación de los métodos <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> y <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>. A continuación, se copia el contenido de la estructura administrada en el búfer no administrado. Por último, se usa el método <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> para calcular referencias de datos desde el búfer no administrado a un objeto administrado y el método <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> para liberar el bloque de memoria no administrada.

### <a name="declaring-prototypes"></a>Declaración de prototipos

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a>Llamadas a funciones

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a>FindFile (ejemplo)

En este ejemplo se muestra cómo pasar una estructura que contiene una segunda estructura insertada a una función no administrada. También se muestra cómo usar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> para declarar una matriz de longitud fija dentro de la estructura. En este ejemplo, los elementos de la estructura insertada se agregan a la estructura primaria. Para obtener un ejemplo de una estructura insertada que no esté simplificada, vea [Ejemplo Structs](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).

En el ejemplo FindFile se usa la siguiente función no administrada, que se muestra con su declaración de función original:

- **FindFirstFile** exportada desde Kernel32.dll.

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

La estructura original pasada a la función contiene los elementos siguientes:

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

En este ejemplo, la clase `FindData` contiene un miembro de datos correspondiente para cada elemento de la estructura original y de la estructura insertada. En lugar de dos búferes de caracteres originales, la clase sustituye cadenas. **MarshalAsAttribute** establece el valor de la enumeración <xref:System.Runtime.InteropServices.UnmanagedType> en **ByValTStr**, que se usa para identificar las matrices de caracteres de longitud fija insertadas que aparecen en las estructuras no administradas.

La clase `NativeMethods` contiene un prototipo administrado del método `FindFirstFile`, que pasa la clase `FindData` como un parámetro. El parámetro se debe declarar con los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> porque las clases, que son tipos de referencia, se pasan como parámetros In de forma predeterminada.

### <a name="declaring-prototypes"></a>Declaración de prototipos

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a>Llamadas a funciones

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a>Unions (ejemplo)

En este ejemplo se muestra cómo pasar estructuras que solo contienen tipos de valor y estructuras que contienen un tipo de valor y una cadena como parámetros para una función no administrada que espera recibir una unión. Una unión representa una ubicación de memoria que puede ser compartida por dos o más variables.

En el ejemplo Unions se usa la siguiente función no administrada, que se muestra con su declaración de función original:

- **TestUnion** exportada desde PinvokeLib.dll.

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) es una biblioteca personalizada no administrada que contiene una implementación para la función enumerada anteriormente y dos uniones, **MYUNION** y **MYUNION2**. Las uniones contienen los siguientes elementos:

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

En código administrado, las uniones se definen como estructuras. La estructura `MyUnion` contiene dos tipos de valor como miembros: un entero y un doble. El atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> está establecido para controlar la posición exacta de cada miembro de datos. El atributo <xref:System.Runtime.InteropServices.FieldOffsetAttribute> proporciona la posición física de los campos dentro de la representación no administrada de una unión. Observe que ambos miembros tienen los mismos valores de desplazamiento, por lo que pueden definir la misma parte de memoria.

`MyUnion2_1` y `MyUnion2_2` contienen un tipo de valor (entero) y una cadena, respectivamente. En código administrado, los tipos de valor y los tipos de referencia no pueden superponerse. En este ejemplo se usa la sobrecarga de métodos para permitir que el llamador utilice ambos tipos cuando llama a la misma función no administrada. El diseño de `MyUnion2_1` es explícito y tiene un valor de desplazamiento preciso. Por el contrario, `MyUnion2_2` tiene un diseño secuencial porque no se permiten diseños explícitos con tipos de referencia. El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> establece el valor de la enumeración <xref:System.Runtime.InteropServices.UnmanagedType> en **ByValTStr**, que se usa para identificar las matrices de caracteres de longitud fija insertadas que aparecen en la representación no administrada de la unión.

La clase `NativeMethods` contiene los prototipos para los métodos `TestUnion` y `TestUnion2`. `TestUnion2` se sobrecarga para declarar `MyUnion2_1` o `MyUnion2_2` como parámetros.

### <a name="declaring-prototypes"></a>Declaración de prototipos

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a>Llamadas a funciones

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="systime-sample"></a>SysTime (ejemplo)

En este ejemplo se muestra cómo pasar un puntero a una clase a una función no administrada que espera recibir un puntero a una estructura.

En el ejemplo SysTime se usa la siguiente función no administrada, que se muestra con su declaración de función original:

- **GetSystemTime** exportada desde Kernel32.dll.

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

La estructura original pasada a la función contiene los elementos siguientes:

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

En este ejemplo, la clase `SystemTime` contiene los elementos de la estructura original representados como miembros de clase. El atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> se establece para garantizar que los miembros se organizan secuencialmente en la memoria, en el orden en que aparecen.

La clase `NativeMethods` contiene un prototipo administrado del método `GetSystemTime`, que pasa la clase `SystemTime` como un parámetro In/Out de forma predeterminada. El parámetro se debe declarar con los atributos <xref:System.Runtime.InteropServices.InAttribute> y <xref:System.Runtime.InteropServices.OutAttribute> porque las clases, que son tipos de referencia, se pasan como parámetros In de forma predeterminada. Para que el autor de la llamada reciba los resultados, deben aplicarse explícitamente estos [atributos direccionales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)). La clase `App` crea una nueva instancia de la clase `SystemTime` y tiene acceso a sus campos de datos.

### <a name="code-samples"></a>Ejemplos de código

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a>OutArrayOfStructs (ejemplo)

En este ejemplo se muestra cómo pasar una matriz de estructuras que contiene enteros y cadenas como parámetros Out a una función no administrada.

En el ejemplo se muestra cómo llamar a una función nativa mediante la clase <xref:System.Runtime.InteropServices.Marshal> y código no seguro.

En este ejemplo se usan funciones de contenedor e invocaciones de plataforma definidas en [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), que también se proporciona en los archivos de origen. Se usa la función `TestOutArrayOfStructs` y la estructura `MYSTRSTRUCT2`. La estructura contiene los siguientes elementos:

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

La clase `MyStruct` contiene un objeto de cadena de caracteres ANSI. El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> especifica el formato ANSI. `MyUnsafeStruct` es una estructura que contiene un tipo <xref:System.IntPtr> en lugar de una cadena.

La clase `NativeMethods` contiene el método de prototipo `TestOutArrayOfStructs` sobrecargado. Si un método declara un puntero como parámetro, la clase se debe marcar con la palabra clave `unsafe`. Puesto que Visual Basic no puede utilizar código no seguro, el método sobrecargado, el modificado unsafe y la estructura `MyUnsafeStruct` no son innecesarios.

La clase `App` implementa el método `UsingMarshaling`, que realiza todas las tareas necesarias para pasar la matriz. La matriz se marca con la palabra clave `out` (`ByRef` en Visual Basic) para indicar que los datos se pasan del destinatario al llamador. La implementación usa los siguientes métodos de la clase <xref:System.Runtime.InteropServices.Marshal>:

- <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> para calcular las referencias de datos desde el búfer no administrado a un objeto administrado.

- <xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> para liberar la memoria reservada para las cadenas en la estructura.

- <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> para liberar la memoria reservada para la matriz.

Como se mencionó anteriormente, C# permite código no seguro y Visual Basic, no. En el ejemplo de C#, `UsingUnsafePointer` es una implementación de método alternativo que usa punteros en lugar de la clase <xref:System.Runtime.InteropServices.Marshal> para devolver la matriz que contiene la estructura `MyUnsafeStruct`.

### <a name="declaring-prototypes"></a>Declaración de prototipos

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a>Llamadas a funciones

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a>Vea también

- [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md)
- [Serialización de cadenas](marshaling-strings.md)
- [Serialización de tipos diferentes de matrices](marshaling-different-types-of-arrays.md)
