---
title: Serialización de datos con invocación de plataforma
ms.date: 07/31/2018
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae8fbb47986e5baaecb919ce79ae384a8427737a
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "48850483"
---
# <a name="marshaling-data-with-platform-invoke"></a>Serialización de datos con invocación de plataforma
Para llamar a las funciones exportadas desde una biblioteca no administrada, una aplicación de .NET Framework requiere un prototipo de función en código administrado que representa la función no administrada. Para crear un prototipo que permita a la invocación de plataforma serializar los datos correctamente, debe hacer lo siguiente:  
  
-   Aplique el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> a la función o método estático en el código administrado.  
  
-   Sustituya los tipos de datos administrados por tipos de datos no administrados.  
  
 Puede usar la documentación suministrada con una función no administrada para construir un prototipo administrado equivalente aplicando el atributo con sus campos opcionales y sustituyendo los tipos de datos administrados por tipos administrados. Para obtener instrucciones sobre cómo aplicar **DllImportAttribute**, vea [Consumir funciones DLL no administradas](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).  
  
 En esta sección se proporcionan ejemplos que muestran cómo crear prototipos de función administrada para pasar argumentos y recibir los valores devueltos de funciones exportadas por bibliotecas no administradas. Los ejemplos demuestran también cuándo usar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> y la clase <xref:System.Runtime.InteropServices.Marshal> para calcular las referencias de los datos de forma explícita.  
  
## <a name="platform-invoke-data-types"></a>Tipos de datos de invocación de plataforma  
 En la tabla siguiente se enumeran los tipos de datos usados en las funciones de estilo C y en la API Win32 (incluida en el archivo Wtypes.h). Muchas bibliotecas no administradas contienen funciones que pasan estos tipos de datos como parámetros y valores devueltos. La tercera columna muestra la clase o el tipo de valor integrado de .NET Framework correspondiente que se usa en el código administrado. En algunos casos, puede sustituir un tipo del mismo tamaño por el tipo indicado en la tabla.  
  
|Tipo no administrado en Wtypes.h|Tipo de lenguaje C no administrado|Nombre de clase administrada|Descripción|  
|--------------------------------|-------------------------------|------------------------|-----------------|  
|**VOID**|**void**|<xref:System.Void?displayProperty=nameWithType>|Se aplica a una función que no devuelve un valor.|
|**HANDLE**|**void \***|<xref:System.IntPtr?displayProperty=nameWithType>|32 bits en sistemas de operativos Windows de 32 bits, 64 bits en sistemas operativos Windows de 64 bits.|  
|**BYTE**|**unsigned char**|<xref:System.Byte?displayProperty=nameWithType>|8 bits|  
|**SHORT**|**short**|<xref:System.Int16?displayProperty=nameWithType>|16 bits|  
|**WORD**|**unsigned short**|<xref:System.UInt16?displayProperty=nameWithType>|16 bits|  
|**INT**|**int**|<xref:System.Int32?displayProperty=nameWithType>|32 bits|  
|**UINT**|**unsigned int**|<xref:System.UInt32?displayProperty=nameWithType>|32 bits|  
|**LONG**|**long**|<xref:System.Int32?displayProperty=nameWithType>|32 bits|  
|**BOOL**|**long**|<xref:System.Byte>|32 bits|  
|**DWORD**|**unsigned long**|<xref:System.UInt32?displayProperty=nameWithType>|32 bits|  
|**ULONG**|**unsigned long**|<xref:System.UInt32?displayProperty=nameWithType>|32 bits|  
|**CHAR**|**char**|<xref:System.Char?displayProperty=nameWithType>|Decorar con ANSI.|  
|**WCHAR**|**wchar_t**|<xref:System.Char?displayProperty=nameWithType>|Decorar con Unicode.|  
|**LPSTR**|**char &ast;**|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorar con ANSI.|  
|**LPCSTR**|**Const char &ast;**|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorar con ANSI.|  
|**LPWSTR**|**wchar_t &ast;**|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorar con Unicode.|  
|**LPCWSTR**|**Const wchar_t &ast;**|<xref:System.String?displayProperty=nameWithType> o <xref:System.Text.StringBuilder?displayProperty=nameWithType>|Decorar con Unicode.|  
|**FLOAT**|**Float**|<xref:System.Single?displayProperty=nameWithType>|32 bits|  
|**DOUBLE**|**Double**|<xref:System.Double?displayProperty=nameWithType>|64 bits|  
  
 Para los tipos correspondientes en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# y C++, vea la [Introducción a la biblioteca de clases de .NET Framework](../../../docs/standard/class-library-overview.md).  
  
## <a name="pinvokelibdll"></a>PinvokeLib.dll  
 El código siguiente define las funciones de biblioteca proporcionadas por Pinvoke.dll. Muchos ejemplos descritos en esta sección llaman a esta biblioteca.  
  
### <a name="example"></a>Ejemplo  
 [!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]  
  
 [!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]
