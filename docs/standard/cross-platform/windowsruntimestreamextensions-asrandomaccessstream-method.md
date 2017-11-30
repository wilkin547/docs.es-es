---
title: "WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
api_name: System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location: System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be93ddc0f3bf0a5079f31bfa0ff5caa882342c37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)
[Compatible con .NET Framework 4.5.1 y versiones posteriores]  
  
 Convierte la secuencia especificada en una secuencia de acceso aleatorio.  
  
 **Namespace:**<xref:System.IO?displayProperty=nameWithType>  
 **Ensamblado:** System.Runtime.WindowsRuntime (de System.Runtime.WindowsRuntime.dll)  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a>Parámetros  
 `stream`  
  
 Tipo: <xref:System.IO.Stream?displayProperty=nameWithType>  
La secuencia que se va a convertir.  
  
## <a name="return-value"></a>Valor devuelto  
 Tipo: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)  
Un [!INCLUDE[wrt](../../../includes/wrt-md.md)] secuencia de acceso aleatorio, que representa la secuencia convertida.  
  
## <a name="exceptions"></a>Excepciones  
  
|Excepción|Condición|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|La secuencia que se va a convertir no admite operaciones de búsqueda.|  
  
## <a name="remarks"></a>Comentarios  
 Este método de extensión solo está disponible al desarrollar aplicaciones de la Tienda Windows. Este método proporciona una forma cómoda de trabajar con secuencias en las aplicaciones de la Tienda Windows. La secuencia de .NET Framework que desea convertir debe admitir operaciones de búsqueda. Para obtener más información, vea el método <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Esta API es compatible con .NET Framework 4.5.1 y versiones posteriores, pero no con la versión 4.5.  
  
## <a name="version-information"></a>Información de versión  
 **.NET para aplicaciones de la tienda de Windows**  
  
 Se admite en: Windows 8.1  
  
## <a name="see-also"></a>Vea también  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
