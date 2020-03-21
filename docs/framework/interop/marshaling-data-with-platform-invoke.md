---
title: Serialización de datos con invocación de plataforma
ms.date: 03/20/2019
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
ms.openlocfilehash: b8c4e9d835db044912d1cbed92a14dd05e7de658
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400948"
---
# <a name="marshaling-data-with-platform-invoke"></a>Serialización de datos con invocación de plataforma

Para llamar a las funciones exportadas desde una biblioteca no administrada, una aplicación de .NET Framework requiere un prototipo de función en código administrado que representa la función no administrada. Para crear un prototipo que permita a la invocación de plataforma serializar los datos correctamente, debe hacer lo siguiente:

- Aplique el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> a la función o método estático en el código administrado.

- Sustituya los tipos de datos administrados por tipos de datos no administrados.

Puede usar la documentación suministrada con una función no administrada para construir un prototipo administrado equivalente aplicando el atributo con sus campos opcionales y sustituyendo los tipos de datos administrados por tipos administrados. Para obtener instrucciones sobre cómo aplicar <xref:System.Runtime.InteropServices.DllImportAttribute>, vea [Consumir funciones DLL no administradas](consuming-unmanaged-dll-functions.md).

En esta sección se proporcionan ejemplos que muestran cómo crear prototipos de función administrada para pasar argumentos y recibir los valores devueltos de funciones exportadas por bibliotecas no administradas. Los ejemplos demuestran también cuándo usar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> y la clase <xref:System.Runtime.InteropServices.Marshal> para calcular las referencias de los datos de forma explícita.

## <a name="platform-invoke-data-types"></a>Tipos de datos de invocación de plataforma

En la tabla siguiente se enumeran los tipos de datos usados en las API de Windows y las funciones de estilo C. Muchas bibliotecas no administradas contienen funciones que pasan estos tipos de datos como parámetros y valores devueltos. La tercera columna muestra la clase o el tipo de valor integrado de .NET Framework correspondiente que se usa en el código administrado. En algunos casos, puede sustituir un tipo del mismo tamaño por el tipo indicado en la tabla.

|Tipo no administrado en las API de Windows|Tipo de lenguaje C no administrado|Tipo administrado|Descripción|
|--------------------------------|-------------------------------|------------------------|-----------------|
|`VOID`|`void`|<xref:System.Void?displayProperty=nameWithType>|Se aplica a una función que no devuelve un valor.|
|`HANDLE`|`void *`|<xref:System.IntPtr?displayProperty=nameWithType> o <xref:System.UIntPtr?displayProperty=nameWithType>|32 bits en sistemas de operativos Windows de 32 bits, 64 bits en sistemas operativos Windows de 64 bits.|
|`BYTE`|`unsigned char`|<xref:System.Byte?displayProperty=nameWithType>|8 bits|
|`SHORT`|`short`|<xref:System.Int16?displayProperty=nameWithType>|16 bits|
|`WORD`|`unsigned short`|<xref:System.UInt16?displayProperty=nameWithType>|16 bits|
|`INT`|`int`|<xref:System.Int32?displayProperty=nameWithType>|32 bits|
|`UINT`|`unsigned int`|<xref:System.UInt32?displayProperty=nameWithType>|32 bits|
|`LONG`|`long`|<xref:System.Int32?displayProperty=nameWithType>|32 bits|
|`BOOL`|`long`|<xref:System.Boolean?displayProperty=nameWithType> o <xref:System.Int32?displayProperty=nameWithType>|32 bits|
|`DWORD`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|32 bits|
|`ULONG`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|32 bits|
|`CHAR`|`char`|<xref:System.Char?displayProperty=nameWithType>|Decorar con ANSI.|
|`WCHAR`|`wchar_t`|<xref:System.Char?displayProperty=nameWithType>|Decorar con Unicode.|
|`LPSTR`|`char *`|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorar con ANSI.|
|`LPCSTR`|`const char *`|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorar con ANSI.|
|`LPWSTR`|`wchar_t *`|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorar con Unicode.|
|`LPCWSTR`|`const wchar_t *`|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorar con Unicode.|
|`FLOAT`|`float`|<xref:System.Single?displayProperty=nameWithType>|32 bits|
|`DOUBLE`|`double`|<xref:System.Double?displayProperty=nameWithType>|64 bits|

Para los tipos correspondientes en Visual Basic, C# y C++, vea la [Introducción a la biblioteca de clases de .NET Framework](../../standard/class-library-overview.md#system-namespace).

## <a name="pinvokelibdll"></a>PinvokeLib.dll

El código siguiente define las funciones de biblioteca proporcionadas por Pinvoke.dll. Muchos ejemplos descritos en esta sección llaman a esta biblioteca.

### <a name="example"></a>Ejemplo

[!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]

[!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]
