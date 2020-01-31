---
title: Procedimientos recomendados de interoperabilidad nativa (.NET)
description: Conozca los procedimientos recomendados para interactuar con componentes nativos en. NET.
ms.date: 01/18/2019
ms.openlocfilehash: 9486256b815856c0c283f5fe231be3d35d6e8f00
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742750"
---
# <a name="native-interoperability-best-practices"></a>Procedimientos recomendados de interoperabilidad nativa

.NET ofrece diversas formas de personalizar el código de interoperabilidad nativa. En este artículo se incluye la guía que siguen los equipos de .NET de Microsoft para realizar la interoperabilidad nativa.

## <a name="general-guidance"></a>Orientación general

La guía de esta sección se aplica a todos los escenarios de interoperabilidad.

- ✔️ usar los mismos nombres y mayúsculas y minúsculas para los métodos y parámetros que el método nativo al que desea llamar.
- ✔️ considere la posibilidad de usar el mismo nombre y uso de mayúsculas para los valores constantes.
- ✔️ usar tipos de .NET que se asignan más cercanos al tipo nativo. Por ejemplo, en C#, utilice `uint` cuando el tipo nativo es `unsigned int`.
- ✔️ solo usan atributos `[In]` y `[Out]` cuando el comportamiento que desea es diferente del comportamiento predeterminado.
- ✔️ considere la posibilidad de usar <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> para agrupar los búferes de la matriz nativa.
- ✔️ considere la posibilidad de ajustar las declaraciones P/Invoke en una clase con el mismo nombre y las mayúsculas y minúsculas que la biblioteca nativa.
  - De esta forma, los atributos `[DllImport]` usan la característica de lenguaje `nameof` de C# para pasar el nombre de la biblioteca nativa y garantizar que no escribió mal el nombre de la biblioteca nativa.

## <a name="dllimport-attribute-settings"></a>Configuración del atributo DllImport

| Configuración de | Predeterminado | Recomendación | Detalles |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  Mantener el valor predeterminado  | Cuando se establece explícitamente en false, los valores devueltos de HRESULT con errores se convierten en excepciones (y el valor devuelto en la definición se convierte en NULL).|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | Depende de la API  | Establezca este valor en true si la API utiliza GetLastError y use Marshal.GetLastWin32Error para obtener el valor. Si la API establece una condición que indica que tiene un error, obtenga el error antes de realizar otras llamadas para evitar que accidentalmente se sobrescriba.|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | `CharSet.None`, que vuelve al comportamiento `CharSet.Ansi`  | Usar explícitamente `CharSet.Unicode` o `CharSet.Ansi` cuando haya cadenas o caracteres en la definición | Esto especifica el comportamiento de serialización de cadenas y lo que `ExactSpelling` hace cuando es `false`. Tenga en cuenta que `CharSet.Ansi` es realmente UTF8 en Unix. _La mayoría de las veces_ Windows utiliza Unicode, mientras que Unix usa UTF8. Obtenga más información en la [documentación de juegos de caracteres](./charset.md). |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | Establezca este valor en true y obtenga una ventaja de rendimiento ligero, ya que el entorno de ejecución no busca nombres de función alternativos con un sufijo "A" o "W" en función del valor de la configuración de `CharSet` ("A" para `CharSet.Ansi` y "W" para `CharSet.Unicode`). |

## <a name="string-parameters"></a>Parámetros de cadena

Cuando el juego de caracteres es Unicode o el argumento se marca explícitamente como `[MarshalAs(UnmanagedType.LPWSTR)]` _y_ la cadena se pasa por valor (no `ref` ni `out`), la cadena se anclará y usará directamente el código nativo (en lugar de copiarse).

Recuerde marcar `[DllImport]` como `Charset.Unicode`, a menos que explícitamente desee un tratamiento ANSI de las cadenas.

❌ no utilizan parámetros de `[Out] string`. Los parámetros de cadena pasados por valor con el atributo `[Out]` pueden llegar a desestabilizar el entorno de ejecución si la cadena es una cadena internalizada. Obtenga más información sobre el internamiento de cadenas en la documentación de <xref:System.String.Intern%2A?displayProperty=nameWithType>.

❌ evitar `StringBuilder` parámetros. La serialización `StringBuilder`*siempre* crea una copia del búfer nativo. Por lo tanto, puede ser extremadamente ineficaz. Siga el escenario típico de una llamada a una API de Windows que toma una cadena:

1. Cree un SB de la capacidad deseada (asigna la capacidad administrada) **{1}** .
2. Invocar
   1. Asigna un búfer nativo **{2}** .
   2. Copia el contenido si `[In]` _(el valor predeterminado de un parámetro `StringBuilder`)_ .
   3. Copia el búfer nativo en una matriz administrada recién asignada si `[Out]` **{3}** _(también el valor predeterminado para `StringBuilder`)_
3. `ToString()` asigna otra matriz administrada **{4}** .

Es decir, asignaciones *{4}* para obtener una cadena del código nativo. Lo mejor que puede hacer para limitar esto consiste en reutilizar `StringBuilder` en otra llamada, pero esta todavía solo guarda la asignación *1*. Es mucho mejor usar y almacenar en caché un búfer de caracteres de `ArrayPool`; después, puede llegar a la asignación de `ToString()` en las llamadas posteriores.

El otro problema con `StringBuilder` es que siempre copia la copia de seguridad del búfer de retorno en el primer valor NULL. Si la cadena pasada anterior no está terminada o es una cadena terminada en doble NULL, el valor P/Invoke será incorrecto en el mejor de los casos.

Si *usa*`StringBuilder`, un último problema es que la capacidad **no** incluyen un valor NULL oculto, que siempre se tiene en cuenta en la interoperabilidad. Es habitual equivocarse, ya que la mayoría de las API quieren que el tamaño del búfer *incluyan* el valor NULL. Esto puede dar lugar a asignaciones innecesarias. Además, este problema impide que el entorno de ejecución optimice la serialización `StringBuilder` para minimizar las copias.

✔️ considere la posibilidad de usar `char[]`s de un `ArrayPool`.

Para obtener más información sobre la serialización cadenas, vea [Cálculo de referencias predeterminado para cadenas](../../framework/interop/default-marshaling-for-strings.md) y [Personalización de la serialización de campos de cadena](customize-parameter-marshaling.md#customizing-string-parameters).

> __Específico de Windows__ Por `[Out]` cadenas que CLR usará `CoTaskMemFree` de forma predeterminada para las cadenas libres o `SysStringFree` para las cadenas marcadas como `UnmanagedType.BSTR`.
> **Para la mayoría de las API con un búfer de cadena de salida:** El recuento de caracteres pasado debe incluir el valor null. Si el valor devuelto es menor que el número de caracteres pasados, la llamada se realiza correctamente y el valor es el número de caracteres *sin* el carácter NULL. En caso contrario, el número es el tamaño del búfer necesario *incluyendo* el carácter NULL.
>
> - Pass en 5, Get 4: la cadena tiene una longitud de 4 caracteres con un valor null final.
> - Pass en 5, Get 6: la cadena tiene una longitud de 5 caracteres; se necesita un búfer de 6 caracteres para contener el valor null.
> [Tipos de datos de Windows para cadenas](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a>Parámetros y campos booleanos

Los valores booleanos se desordenan fácilmente. De forma predeterminada, .NET `bool` se serializa en un valor `BOOL` de Windows de 4 bytes. Sin embargo, los tipos `_Bool` y `bool` en C y C++ tienen un *solo* byte. De este modo, puede ser complicado realizar un seguimiento de los errores porque la mitad del valor devuelto se descarta, con lo que *posiblemente* se modifica el resultado. Para obtener más información sobre la serialización de valores `bool` de .NET en tipos `bool` de C o C++, vea la documentación sobre [cómo personalizar la serialización de campos booleanos](customize-struct-marshaling.md#customizing-boolean-field-marshaling).

## <a name="guids"></a>GUID

Los GUID se pueden usar directamente en las firmas. Muchas de las API de Windows toman los alias de tipo `GUID&` como `REFIID`. Cuando se pasan por referencia, se pueden pasar por `ref` o con el atributo `[MarshalAs(UnmanagedType.LPStruct)]`.

| GUID | GUID por referencia |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

❌ no usan `[MarshalAs(UnmanagedType.LPStruct)]` para ningún elemento que no sea `ref` parámetros GUID.

## <a name="blittable-types"></a>Tipos que pueden transferirse en bloque de bits

Los tipos que pueden transferirse en bloque de bits son tipos que tienen la misma representación de nivel de bits en código administrado y nativo. Por lo tanto, no es necesario convertirlos a otro formato para serializarlos con código nativo como punto de partida o destino, y como se mejora el rendimiento, deben preferirse estos tipos.

**Tipos que pueden transferirse en bloque de bits:**

- `byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`
- Matrices unidimensionales no anidadas de tipos que puede transferirse en bloque de bits (por ejemplo, `int[]`).
- Estructuras y clases con distribución fija que solo tienen tipos de valor que pueden transferirse en bloque de bits, por ejemplo, campos.
  - La distribución fija requiere `[StructLayout(LayoutKind.Sequential)]` o `[StructLayout(LayoutKind.Explicit)]`.
  - De forma predeterminada, las estructuras son `LayoutKind.Sequential` y las clases, `LayoutKind.Auto`.

**Tipos que no se pueden transferir en bloque de bits:**

- `bool`

**Tipos que A VECES se pueden transferir en bloque de bits:**

- `char`, `string`

Cuando se pasan tipos que pueden transferirse en bloque de bits por referencia, está anclados simplemente por el serializador en lugar de estar copiados en un búfer intermedio. Las clases se pasan intrínsecamente por referencia y las estructuras se pasan por referencia cuando se usa con `ref` o `out`.

`char` puede transferirse en bloque de bits en una matriz unidimensional **o** si forma parte de un tipo que lo contiene, se marca explícitamente con `[StructLayout]` con `CharSet = CharSet.Unicode`.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

`string` puede transferirse en bloque de bits si no está contenido en otro tipo y si se pasa como un argumento que se marca con `[MarshalAs(UnmanagedType.LPWStr)]` o `[DllImport]` tiene `CharSet = CharSet.Unicode` establecido.

Puede ver si un tipo puede transferirse en bloque de bits al intentar crear un controlador `GCHandle` anclado. Si el tipo no es una cadena o no puede transferirse en bloque de bits, `GCHandle.Alloc` producirá una excepción `ArgumentException`.

✔️ hacer que las estructuras sean representables en bytes siempre que sea posible.

Para obtener más información, vea:

- [Tipos que pueden o que no pueden transferirse en bloque de bits](../../framework/interop/blittable-and-non-blittable-types.md)
- [Serialización de tipos](type-marshaling.md)

## <a name="keeping-managed-objects-alive"></a>Forma de mantener activos los objetos administrados

`GC.KeepAlive()` asegurará que un objeto permanezca dentro del ámbito hasta que se alcance el método KeepAlive.

[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) permite que el serializador mantenga un objeto activo para la duración de P/Invoke. Se puede usar en lugar de `IntPtr` en firmas de método. `SafeHandle` reemplaza esta clase de forma eficaz y se debe usar en su lugar.

[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) permite anclar un objeto administrado y obtener el puntero nativo. El patrón básico es el siguiente:

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

Anclar no es la acción predeterminada para `GCHandle`. El otro patrón principal se usa para pasar una referencia a un objeto administrado a través de código nativo y devolverse al código administrado, normalmente con una devolución de llamada. Este es el patrón:

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

No olvide que `GCHandle` debe liberarse explícitamente para evitar fugas de memoria.

## <a name="common-windows-data-types"></a>Tipos de datos de Windows comunes

Esta es una lista de los tipos de datos que se usan frecuentemente en las API de Windows y los tipos de C# que se deben usar al llamar al código de Windows.

Los siguientes tipos tienen el mismo tamaño en Windows 32 bits y 64 bits, a pesar de sus nombres.

| Ancho | Portal          | C (Windows)          | C#       | Alternativa                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| 32    | `BOOL`           | `int`                | `int`    | `bool`                               |
| 8     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| 8     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| 8     | `CHAR`           | `char`               | `sbyte`  |                                      |
| 8     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| 16    | `SHORT`          | `short`              | `short`  |                                      |
| 16    | `CSHORT`         | `short`              | `short`  |                                      |
| 16    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| 16    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| 16    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| 32    | `INT`            | `int`                | `int`    |                                      |
| 32    | `LONG`           | `long`               | `int`    |                                      |
| 32    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| 32    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| 64    | `QWORD`          | `long long`          | `long`   |                                      |
| 64    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| 64    | `LONGLONG`       | `long long`          | `long`   |                                      |
| 64    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| 64    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| 32    | `HRESULT`        | `long`               | `int`    |                                      |
| 32    | `NTSTATUS`       | `long`               | `int`    |                                      |

Los siguientes tipos, que son punteros, siguen el ancho de la plataforma. Use `IntPtr`/`UIntPtr` para estos.

| Tipos de puntero con signo (use `IntPtr`) | Tipos de puntero sin signo (use `UIntPtr`) |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

Un tipo `PVOID` de Windows que es un tipo `void*` de C se pueden serializar como `IntPtr` o `UIntPtr`, pero prefiere `void*` cuando sea posible.

[Tipos de datos de Windows](/windows/desktop/WinProg/windows-data-types)

[Intervalos de tipo de datos](/cpp/cpp/data-type-ranges)

## <a name="structs"></a>Structs

Las estructuras administradas se crean en la pila y no se quitan hasta que el método se devuelve. Por definición, se anclan (la recolección de elementos no utilizados no las mueve). Puede simplemente tomar la dirección en bloques de código no seguros si el código nativo no utilizará el puntero más allá del final del método actual.

Las estructuras que pueden transferirse en bloque de bits son mucho más eficaces, ya que solo puede utilizarlas directamente la capa de serialización. Trate de crear estructuras que pueden transferirse en bloque de bits (por ejemplo, evite `bool`). Para obtener más información, consulte la sección [Tipos que pueden transferirse en bloque de bits](#blittable-types).

*Si* la estructura se puede transferir en bloque de bits, use `sizeof()` en lugar de `Marshal.SizeOf<MyStruct>()` para mejorar el rendimiento. Como se mencionó anteriormente, puede validar que el tipo se pueda transferir en bloques de bits al intentar crear un controlador `GCHandle` anclado. Si el tipo no es una cadena o no puede transferirse en bloque de bits, `GCHandle.Alloc` producirá una excepción `ArgumentException`.

Los punteros a las estructuras en definiciones deben pasarse por `ref` o usar `unsafe` y `*`.

✔️ coinciden con el struct administrado lo más cerca posible de la forma y los nombres que se usan en la documentación o el encabezado de la plataforma oficial.

✔️ usar el C# `sizeof()` en lugar de `Marshal.SizeOf<MyStruct>()` para las estructuras que se pueden retrasar para mejorar el rendimiento.

Una matriz como `INT_PTR Reserved1[2]` tiene que serializarse a dos campos `IntPtr`, `Reserved1a` y `Reserved1b`. Cuando la matriz nativa es un tipo primitivo, podemos usar la palabra clave `fixed` para escribir de forma más limpia. Por ejemplo, `SYSTEM_PROCESS_INFORMATION` tiene este aspecto en el encabezado nativo:

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

En C#, podemos escribirlo así:

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

Sin embargo, existen los búferes fijos tienen algunas trampas. Los búferes fijos de tipos que no pueden transferirse en bloques de bits no se serializarán correctamente, por lo que la matriz en contexto debe expandirse a varios campos individuales. Además, en .NET Framework y .NET Core antes de la versión 3.0, si una estructura que contiene un campo de búfer fijo se anida dentro de una estructura que no puede transferirse en bloque de bits, el campo de búfer fijo no se serializará correctamente al código nativo.
