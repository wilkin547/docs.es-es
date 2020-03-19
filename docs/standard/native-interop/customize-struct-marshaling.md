---
title: 'Personalización de la serialización de estructuras: .NET'
description: Obtenga información sobre cómo personalizar la forma en que .NET serializa las estructuras de una representación nativa.
ms.date: 01/18/2019
dev_langs:
- csharp
- cpp
ms.openlocfilehash: 7f8d1ad93633d6feef9c3c6f5d19aad52105968c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401170"
---
# <a name="customizing-structure-marshaling"></a>Personalización de la serialización de estructuras

A veces, las reglas de serialización predeterminadas para las estructuras no es exactamente lo que necesita. Los entornos de ejecución de .NET proporcionan unos puntos de extensión que permiten personalizar el diseño de la estructura y cómo se serializan los campos.

## <a name="customizing-structure-layout"></a>Personalización del diseño de estructuras

.NET proporciona el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> y la enumeración <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType> para poder personalizar cómo se colocan los campos en la memoria. Las siguientes instrucciones lo ayudarán a evitar problemas comunes.

✔️ PLANTÉESE  usar `LayoutKind.Sequential` siempre que sea posible.

✔️ USE  solo `LayoutKind.Explicit` en la serialización cuando la estructura nativa tenga un diseño explícito, como una unión.

❌EVITAR `LayoutKind.Explicit` el uso de serializaciones al calcular el cálculo de referencias de estructuras en plataformas que no sean Windows si necesita tener como destino tiempos de ejecución antes de .NET Core 3.0. El tiempo de ejecución de .NET Core anterior a 3.0 no admite pasar estructuras explícitas por valor a funciones nativas en sistemas Intel o AMD de 64 bits que no sean Windows. Sin embargo, el entorno de ejecución admite pasar estructuras explícitas por referencia en todas las plataformas.

## <a name="customizing-boolean-field-marshaling"></a>Personalización de la serialización de campos booleanos

El código nativo tiene muchas representaciones booleanas diferentes. En Windows, hay tres formas de representar valores booleanos. El entorno de ejecución no sabe la definición nativa de la estructura, por lo que se recomienda realizar una estimación sobre cómo serializar los valores booleanos. El entorno de ejecución de .NET proporciona una manera de indicar cómo serializar el campo booleano. En los ejemplos siguientes se muestra cómo serializar el tipo `bool` de .NET a diferentes tipos nativos booleanos.

Los valores booleanos tienen como valor predeterminado [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL) el cálculo de referencias como un valor Win32 nativo de 4 bytes, como se muestra en el ejemplo siguiente:

```csharp
public struct WinBool
{
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

Si desea ser explícito, puede usar el valor <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType> para obtener el mismo comportamiento que el anterior:

```csharp
public struct WinBool
{
    [MarshalAs(UnmanagedType.Bool)]
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

Mediante los valores `UnmanagedType.U1` o `UnmanagedType.I1`, puede indicar el entorno de ejecución para serializar el campo `b` como un tipo `bool` nativo de 1 byte.

```csharp
public struct CBool
{
    [MarshalAs(UnmanagedType.U1)]
    public bool b;
}
```

```cpp
struct CBool
{
    public bool b;
};
```

En Windows, puede usar el valor <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType> para indicar al entorno de ejecución que serialice el valor booleano a un valor `VARIANT_BOOL` de 2 bytes:

```csharp
public struct VariantBool
{
    [MarshalAs(UnmanagedType.VariantBool)]
    public bool b;
}
```

```cpp
struct VariantBool
{
    public VARIANT_BOOL b;
};
```

> [!NOTE]
> `VARIANT_BOOL` es diferente de la mayoría de los tipos booleanos de `VARIANT_TRUE = -1` y `VARIANT_FALSE = 0`. Además, todos los valores que no son iguales a `VARIANT_TRUE` se consideran false.

## <a name="customizing-array-field-marshaling"></a>Personalización de la serialización de campos de matriz

.NET también incluye algunos ejemplos de cómo personalizar la serialización de matrices.

De forma predeterminada, .NET serializa las matrices como un puntero a una lista contigua de elementos:

```csharp
public struct DefaultArray
{
    public int[] values;
}
```

```cpp
struct DefaultArray
{
    int* values;
};
```

Si está interactuando con API de COM, es posible que deba serializar las matrices como objetos `SAFEARRAY*`. Puede usar <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> y el valor <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> para indicar al entorno de ejecución que serialice una matriz como `SAFEARRAY*`:

```csharp
public struct SafeArrayExample
{
    [MarshalAs(UnmanagedType.SafeArray)]
    public int[] values;
}
```

```cpp
struct SafeArrayExample
{
    SAFEARRAY* values;
};
```

Si necesita personalizar qué tipo de elemento se encuentra en `SAFEARRAY`, puede usar los campos <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> y <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> para personalizar el elemento exacto de `SAFEARRAY`.

Si necesita serializar la matriz en contexto, puede usar el valor <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> para indicar el serializador con el fin de serializar la matriz en contexto. Cuando se usa esta serialización, también se debe proporcionar un valor al campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> del número de elementos de la matriz para que el entorno de ejecución pueda asignar correctamente espacio para la estructura.

```csharp
public struct InPlaceArray
{
    [MarshalAs(UnmanagedType.ByValArray, SizeConst = 4)]
    public int[] values;
}
```

```cpp
struct InPlaceArray
{
    int values[4];
};
```

> [!NOTE]
> .NET no admite la serialización de un campo de matriz de longitud variable como un miembro de matriz flexible C99.

## <a name="customizing-string-field-marshaling"></a>Personalización de la serialización de campos de cadena

.NET también proporciona una amplia variedad de personalizaciones para serializar los campos de cadena.

De forma predeterminada, .NET serializa una cadena como un puntero a una cadena terminada en un valor NULL. La codificación depende del valor del campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> en <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>. Si no se especifica ningún atributo, la codificación predeterminada es una codificación ANSI.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char* str;
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

Si necesita utilizar codificaciones diferentes para los distintos campos o simplemente prefiere ser más explícito en la definición de estructuras, puede usar los valores <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> en un atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>.

```csharp
public struct AnsiString
{
    [MarshalAs(UnmanagedType.LPStr)]
    public string str;
}
```

```cpp
struct AnsiString
{
    char* str;
};
```

```csharp
public struct UnicodeString
{
    [MarshalAs(UnmanagedType.LPWStr)]
    public string str;
}
```

```cpp
struct UnicodeString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

Si desea serializar las cadenas mediante la codificación UTF-8, puede usar el valor <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> en <xref:System.Runtime.InteropServices.MarshalAsAttribute>.

```csharp
public struct UTF8String
{
    [MarshalAs(UnmanagedType.LPUTF8Str)]
    public string str;
}
```

```cpp
struct UTF8String
{
    char* str;
};
```

> [!NOTE]
> El uso de <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> requiere .NET Framework 4.7 (o versiones posteriores) o .NET Core 1.1 (o versiones posteriores). No está disponible en .NET Standard 2.0.

Si está trabajando con API de COM, es posible que deba serializar una cadena como `BSTR`. Mediante el valor <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType>, se puede serializar una cadena como `BSTR`.

```csharp
public struct BString
{
    [MarshalAs(UnmanagedType.BStr)]
    public string str;
}
```

```cpp
struct BString
{
    BSTR str;
};
```

Cuando se usa una API basada en WinRT, es posible que deba serializar una cadena como `HSTRING`.  Mediante el valor <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType>, se puede serializar una cadena como `HSTRING`.

```csharp
public struct HString
{
    [MarshalAs(UnmanagedType.HString)]
    public string str;
}
```

```cpp
struct BString
{
    HSTRING str;
};
```

Si la API requiere que se pase la cadena en contexto en la estructura, puede usar el valor <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType>. Tenga en cuenta que la codificación de una cadena serializada por `ByValTStr` viene determinada por el atributo `CharSet`. Además, requiere que una longitud de cadena se pasa por el campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType>.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char str[4];
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t str[4]; // Could also be wchar_t[4] on Windows.
};
```

## <a name="customizing-decimal-field-marshaling"></a>Personalización de la serialización de campos de decimal

Si está trabajando en Windows, es posible que [ `CY` encuentre `CURRENCY` ](/windows/win32/api/wtypes/ns-wtypes-cy~r1) algunas API que usan el nativo o la estructura. De forma predeterminada, `decimal` el tipo .NET se calcula en la estructura nativa. [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1) Sin embargo, puede usar <xref:System.Runtime.InteropServices.MarshalAsAttribute> con el valor <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType> para indicar al serializador que convierta un valor `decimal` al valor `CY` nativo.

```csharp
public struct Currency
{
    [MarshalAs(UnmanagedType.Currency)]
    public decimal dec;
}
```

```cpp
struct Currency
{
    CY dec;
};
```

## <a name="marshaling-systemobjects"></a>Serialización de `System.Object`

En Windows, puede serializar campos con tipo `object` al código nativo. Puede serializar estos campos a uno de los tres tipos:

- [`VARIANT`](/windows/win32/api/oaidl/ns-oaidl-variant)
- [`IUnknown*`](/windows/desktop/api/unknwn/nn-unknwn-iunknown)
- [`IDispatch*`](/windows/desktop/api/oaidl/nn-oaidl-idispatch)

De forma predeterminada, un campo con tipo `object` se serializará a uno de tipo `IUnknown*` que encapsula el objeto.

```csharp
public struct ObjectDefault
{
    public object obj;
}
```

```cpp
struct ObjectDefault
{
    IUnknown* obj;
};
```

Si desea serializar un campo de objeto a `IDispatch*`, agregue <xref:System.Runtime.InteropServices.MarshalAsAttribute> con el valor <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>.

```csharp
public struct ObjectDispatch
{
    [MarshalAs(UnmanagedType.IDispatch)]
    public object obj;
}
```

```cpp
struct ObjectDispatch
{
    IDispatch* obj;
};
```

Si quiere serializarlo como `VARIANT`, agregue <xref:System.Runtime.InteropServices.MarshalAsAttribute> con el valor <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>.

```csharp
public struct ObjectVariant
{
    [MarshalAs(UnmanagedType.Struct)]
    public object obj;
}
```

```cpp
struct ObjectVariant
{
    VARIANT obj;
};
```

En la tabla siguiente se describen los diferentes tipos en tiempo de ejecución del campo `obj` se asignan a los distintos tipos que se almacenan en `VARIANT`:

| Tipo .NET | Tipo de VARIANTE | | Tipo .NET | Tipo de VARIANTE |
|------------|--------------|-|----------|--------------|
|  `byte`  | `VT_UI1` |     | `System.Runtime.InteropServices.BStrWrapper` | `VT_BSTR` |
| `sbyte`  | `VT_I1`  |     | `object`  | `VT_DISPATCH` |
| `short`  | `VT_I2`  |     | `System.Runtime.InteropServices.UnknownWrapper` | `VT_UNKNOWN` |
| `ushort` | `VT_UI2` |     | `System.Runtime.InteropServices.DispatchWrapper` | `VT_DISPATCH` |
| `int`    | `VT_I4`  |     | `System.Reflection.Missing` | `VT_ERROR` |
| `uint`   | `VT_UI4` |     | `(object)null` | `VT_EMPTY` |
| `long`   | `VT_I8`  |     | `bool` | `VT_BOOL` |
| `ulong`  | `VT_UI8` |     | `System.DateTime` | `VT_DATE` |
| `float`  | `VT_R4`  |     | `decimal` | `VT_DECIMAL` |
| `double` | `VT_R8`  |     | `System.Runtime.InteropServices.CurrencyWrapper` | `VT_CURRENCY` |
| `char`   | `VT_UI2` |     | `System.DBNull` | `VT_NULL` |
| `string` | `VT_BSTR`|
