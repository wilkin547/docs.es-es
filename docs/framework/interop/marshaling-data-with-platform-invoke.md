---
title: "Marshaling Data with Platform Invoke | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "platform invoke, marshaling data"
  - "data marshaling, platform invoke"
  - "marshaling, platform invoke"
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Marshaling Data with Platform Invoke
Para llamar a las funciones exportadas desde una biblioteca no administrada, una aplicación de .NET Framework requiere un prototipo de función en código administrado que representa la función no administrada.  Para crear un prototipo que permita a la invocación de plataforma calcular las referencias de los datos correctamente, debe hacer lo siguiente:  
  
-   Aplique el atributo [DLLImportAttribute](frlrfSystemRuntimeInteropServicesDllImportAttributeClassTopic) a la función o método estático en el código administrado.  
  
-   Sustituya los tipos de datos administrados por tipos de datos no administrados.  
  
 Puede usar la documentación suministrada con una función no administrada para construir un prototipo administrado equivalente aplicando el atributo con sus campos opcionales y sustituyendo los tipos de datos administrados por tipos administrados.  Para obtener instrucciones sobre cómo aplicar **DllImportAttribute**, consulte [Consumir funciones DLL no administradas](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).  
  
 En esta sección se proporcionan ejemplos que muestran cómo crear prototipos de función administrada para pasar argumentos y recibir los valores devueltos de funciones exportadas por bibliotecas no administradas.  Los ejemplos demuestran también cuándo usar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> y la clase <xref:System.Runtime.InteropServices.Marshal> para calcular las referencias de los datos de forma explícita.  
  
## Tipos de datos de invocación de plataforma  
 En la tabla siguiente se enumeran los tipos de datos usados en las funciones de estilo C y en la API Win32 \(incluida en el archivo Wtypes.h\).  Muchas bibliotecas no administradas contienen funciones que pasan estos tipos de datos como parámetros y valores devueltos.  La tercera columna muestra la clase o el tipo de valor integrado de .NET Framework correspondiente que se usa en el código administrado.  En algunos casos, puede sustituir un tipo del mismo tamaño por el tipo indicado en la tabla.  
  
|Tipo no administrado en Wtypes.h|Tipo de lenguaje C no administrado|Nombre de clase administrada|Descripción|  
|--------------------------------------|----------------------------------------|----------------------------------|-----------------|  
|**HANDLE**|**void\***|<xref:System.IntPtr?displayProperty=fullName>|32 bits en sistemas de operativos Windows de 32 bits, 64 bits en sistemas operativos Windows de 64 bits.|  
|**BYTE**|**unsigned char**|<xref:System.Byte?displayProperty=fullName>|8 bits|  
|**SHORT**|**short**|<xref:System.Int16?displayProperty=fullName>|16 bits|  
|**WORD**|**unsigned short**|<xref:System.UInt16?displayProperty=fullName>|16 bits|  
|**INT**|**int**|<xref:System.Int32?displayProperty=fullName>|32 bits|  
|**UINT**|**unsigned int**|<xref:System.UInt32?displayProperty=fullName>|32 bits|  
|**LONG**|**long**|<xref:System.Int32?displayProperty=fullName>|32 bits|  
|**BOOL**|**long**|[\<caps:sentence id\="tgt48" sentenceid\="f5f846452032b75e5fcec49a05fe125a" class\="tgtSentence"\>System.Int32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|32 bits|  
|**DWORD**|**unsigned long**|<xref:System.UInt32?displayProperty=fullName>|32 bits|  
|**ULONG**|**unsigned long**|<xref:System.UInt32?displayProperty=fullName>|32 bits|  
|**CHAR**|**char**|<xref:System.Char?displayProperty=fullName>|Decorar con ANSI.|  
|**WCHAR**|**wchar\_t**|<xref:System.Char?displayProperty=fullName>|Decorar con Unicode.|  
|**LPSTR**|**char\***|<xref:System.String?displayProperty=fullName> o <xref:System.Text.StringBuilder?displayProperty=fullName>|Decorar con ANSI.|  
|**LPCSTR**|**Const char\***|<xref:System.String?displayProperty=fullName> o <xref:System.Text.StringBuilder?displayProperty=fullName>|Decorar con ANSI.|  
|**LPWSTR**|**wchar\_t\***|<xref:System.String?displayProperty=fullName> o <xref:System.Text.StringBuilder?displayProperty=fullName>|Decorar con Unicode.|  
|**LPCWSTR**|**Const wchar\_t\***|<xref:System.String?displayProperty=fullName> o <xref:System.Text.StringBuilder?displayProperty=fullName>|Decorar con Unicode.|  
|**FLOAT**|**Flotante**|<xref:System.Single?displayProperty=fullName>|32 bits|  
|**DOUBLE**|**Doble**|<xref:System.Double?displayProperty=fullName>|64 bits|  
  
 Para los tipos correspondientes en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# y C\+\+, consulte la [Introducción a la biblioteca de clases de .NET Framework](../../../docs/standard/class-library-overview.md).  
  
## PinvokeLib.dll  
 El código siguiente define las funciones de biblioteca proporcionadas por Pinvoke.dll.  Muchos ejemplos descritos en esta sección llaman a esta biblioteca.  
  
### Ejemplo  
 [!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]  
  
 [!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]