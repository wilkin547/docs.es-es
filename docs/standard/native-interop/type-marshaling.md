---
title: 'Serialización de tipos: .NET'
description: Obtenga información sobre cómo .NET serializa los tipos en una representación nativa.
ms.date: 01/18/2019
ms.openlocfilehash: 7fc3dfe950ecd3ed0ff5e4eb0e101c1596a831e1
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441003"
---
# <a name="type-marshaling"></a>Serialización de tipos

La **serialización** es el proceso de transformación de tipos cuando tienen que cruzar el límite entre administrado y nativo.

La serialización es necesaria porque los tipos del código administrado y del código no administrado son diferentes. En el código administrado, por ejemplo, tiene `String`, mientras que en el entorno no administrado, las cadenas pueden ser Unicode ("anchas"), no Unicode, terminadas en un valor nulo, ASCII, etc. De forma predeterminada, el subsistema de P/Invoke intenta hacer "lo correcto" según el comportamiento predeterminado, tal y como se describe en este artículo. Pero en aquellas situaciones en las que necesita un control adicional, puede emplear el atributo [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) para especificar qué tipo se espera en el lado no administrado. Por ejemplo, si queremos que la cadena se envíe como una cadena ANSI terminada en un valor nulo, podemos hacerlo de la manera siguiente:

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshaling-common-types"></a>Reglas predeterminadas para serializar tipos comunes

Por lo general, el entorno de ejecución intenta hacer "lo correcto" al serializar para requerir la menor cantidad de trabajo. En las tablas siguientes se describen cómo se serializa cada tipo de forma predeterminada cuando se utiliza en un parámetro o campo. El entero de ancho fijo C99/C++11 y los tipos de caracteres se usan para garantizar que la tabla siguiente es correcta para todas las plataformas. Puede usar cualquier tipo nativo que tenga la misma alineación y los requisitos de tamaño que estos tipos.

Esta primera tabla describe las asignaciones para distintos tipos en los que la serialización es la misma que en la serialización de campos y de P/Invoke.

| Tipo de .NET | Tipo nativo  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | `char` o `char16_t` según el elemento `CharSet` de la estructura o P/Invoke. Consulte la [documentación de juego de caracteres](charset.md). |
| `string`  | `char*` o `char16_t*` según el elemento `CharSet` de la estructura o P/Invoke. Consulte la [documentación de juego de caracteres](charset.md). |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| Tipos de puntero de .NET (por ejemplo, `void*`)  | `void*` |
| Tipo derivado de `System.Runtime.InteropServices.SafeHandle` | `void*` |
| Tipo derivado de `System.Runtime.InteropServices.CriticalHandle` | `void*`          |
| `bool`    | Tipo `BOOL` de Win32       |
| `decimal` | Estructura `DECIMAL` de COM |
| Delegado de .NET | Puntero de función nativa |
| `System.DateTime` | Tipo `DATE` de Win32 |
| `System.Guid` | Tipo `GUID` de Win32 |

Algunas categorías de serialización tienen distintos valores predeterminados si está serializando un parámetro o una estructura.

| Tipo de .NET | Tipo nativo (parámetro) | Tipo nativo (campo) |
|-----------|-------------------------|---------------------|
| Matriz de .NET | Un puntero al inicio de una matriz de representaciones nativas de los elementos de matriz. | No se permite sin un atributo `[MarshalAs]`|
| Una clase con `LayoutKind` de `Sequential` o `Explicit` | Un puntero a la representación nativa de la clase | Representación nativa de la clase |

En la tabla siguiente se incluyen las reglas de serialización predeterminadas que son solo de Windows. En las plataformas que no sean Windows, no puede serializar estos tipos.

| Tipo de .NET | Tipo nativo (parámetro) | Tipo nativo (campo) |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | Interfaz COM | No se permite sin un atributo `[MarshalAs]` |
| `System.ArgIterator` | `va_list` | No permitido |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | No permitido |
| `System.Collections.IEnumerable` | `IDispatch*` | No permitido |
| `System.DateTimeOffset` | `int64_t` que representa el número de tics desde la medianoche del 1 de enero de 1601 | `int64_t` que representa el número de tics desde la medianoche del 1 de enero de 1601 |

Algunos tipos solo pueden serializarse como parámetros y no como campos. Estas herramientas se muestran en la tabla siguiente:

| Tipo de .NET | Tipo nativo (solo parámetros) |
|-----------|------------------------------|
| `System.Text.StringBuilder` | `char*` o `char16_t*` según el elemento `CharSet` de P/Invoke.  Consulte la [documentación de juego de caracteres](charset.md). |
| `System.ArgIterator` | `va_list` (solo en Windows x86/x64/arm64) |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

Si estos valores predeterminados no hacen exactamente lo que desea, puede personalizar cómo serializar los parámetros. El artículo sobre [serialización de parámetros](customize-parameter-marshaling.md) explica cómo personalizar la forma en que se serializan los diferentes tipos de parámetro.

## <a name="default-marshaling-in-com-scenarios"></a>Serialización predeterminada en escenarios de COM

Cuando se llama a métodos en objetos COM en .NET, el runtime de .NET cambia las reglas de serialización predeterminadas para que coincidan con la semántica común de COM. En la tabla siguiente se enumeran las reglas que usan los runtime de .NET en escenarios de COM:

| Tipo de .NET | Tipo nativo (llamadas a métodos COM) |
|-----------|--------------------------------|
| `bool`    | `VARIANT_BOOL`                 |
| `StringBuilder` | `LPWSTR`                 |
| `string`  | `BSTR`                         |
| Tipos delegados | `_Delegate*` en .NET Framework. No se permite en .NET Core, ni en .NET 5 y versiones posteriores. |
| `System.Drawing.Color` | `OLECOLOR`        |
| Matriz de .NET | `SAFEARRAY`                   |
| `string[]` | `SAFEARRAY` de `BSTR`        |

## <a name="marshaling-classes-and-structs"></a>Serializar clases y estructuras

Otro aspecto de la serialización de tipos es cómo pasar una estructura a un método no administrado. Por ejemplo, algunos métodos no administrados requieren una estructura como parámetro. En estos casos, debemos crear una clase o una estructura correspondiente en la parte administrada del entorno para usarla como un parámetro. Pero no basta con definir simplemente la clase. También es necesario indicarle al contador de referencias cómo asignar campos de la clase a la estructura no administrada. Aquí el atributo `StructLayout` resulta útil.

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

En el ejemplo anterior se muestra un ejemplo simple de una llamada a la función `GetSystemTime()`. La parte interesante está en la línea 4. El atributo especifica que los campos de la clase se deben asignar secuencialmente a la estructura en el otro lado (el lado no administrado). Esto significa que la denominación de los campos no es importante. Solo su orden es importante, ya que es necesario que coincida con la estructura no administrada, tal como se muestra en el siguiente ejemplo:

```c
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

A veces, la serialización predeterminada para la estructura no hace lo que necesita. El artículo [Personalización de la serialización de estructuras](./customize-struct-marshaling.md) le enseña cómo personalizar para serializar una estructura.
