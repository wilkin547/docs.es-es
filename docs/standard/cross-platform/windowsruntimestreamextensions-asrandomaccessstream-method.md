---
title: "WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (M&#233;todo) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream"
apilocation: 
  - "System.Runtime.WindowsRuntime.dll"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (M&#233;todo)
\[Compatible con .NET Framework 4.5.1 y versiones posteriores\]  
  
 Convierte la secuencia especificada en una secuencia de acceso aleatorio.  
  
 **Espacio de nombres:** <xref:System.IO?displayProperty=fullName>   
 **Ensamblado:** System.Runtime.WindowsRuntime \(en System.Runtime.WindowsRuntime.dll\)  
  
## Sintaxis  
  
```csharp  
[CLSCompliantAttribute(false)] public static  IRandomAccessStream AsRandomAccessStream(Stream stream)   
```  
  
```vb  
'Declaration <ExtensionAttribute> _ <CLSCompliantAttribute(False)> _ Public Shared Function AsRandomAccessStream ( _         stream As Stream) As IRandomAccessStream   
```  
  
#### Parámetros  
 `stream`  
  
 Tipo: <xref:System.IO.Stream?displayProperty=fullName>   
 La secuencia que se va a convertir.  
  
## Valor devuelto  
 Tipo: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)   
 Una secuencia de acceso aleatorio de [!INCLUDE[wrt](../../../includes/wrt-md.md)], que representa la secuencia convertida.  
  
## Excepciones  
  
|Excepción|Condición|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|La secuencia que se va a convertir no admite operaciones de búsqueda.|  
  
## Comentarios  
 Este método de extensión solo está disponible al desarrollar aplicaciones de la Tienda Windows.  Este método proporciona una forma cómoda de trabajar con secuencias en las aplicaciones de la Tienda Windows.  La secuencia de .NET Framework que desea convertir debe admitir operaciones de búsqueda.  Para obtener más información, vea el método <xref:System.IO.Stream.Seek%2A?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  Esta API es compatible con .NET Framework 4.5.1 y versiones posteriores, pero no con la versión 4.5.  
  
## Información de versiones  
 **.NET para aplicaciones de la Tienda Windows**  
  
 Compatible con: Windows 8.1  
  
## Vea también  
 <xref:System.IO.WindowsRuntimeStreamExtensions>   
 [Cómo: Convertir flujos de .NET Framework en flujos de Windows en tiempo de ejecución, y viceversa](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)