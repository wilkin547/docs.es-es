---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a712414163446606cbc93154bc821d3b1166fe8f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43800091"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) (Método)

[Compatible con .NET Framework 4.5.1 y versiones posteriores]

Convierte la secuencia especificada en una secuencia de acceso aleatorio.

**Namespace:** <xref:System.IO?displayProperty=nameWithType> 
 **ensamblado:** System.Runtime.WindowsRuntime (en System.Runtime.WindowsRuntime.dll)

## <a name="syntax"></a>Sintaxis

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a>Parámetros

`stream`

Tipo: <xref:System.IO.Stream?displayProperty=nameWithType>  
La secuencia que se va a convertir.

## <a name="return-value"></a>Valor devuelto

Tipo: <xref:Windows.Storage.Streams.RandomAccessStream>  
Un [!INCLUDE[wrt](../../../includes/wrt-md.md)] secuencia de acceso aleatorio, que representa la secuencia convertida.

## <a name="exceptions"></a>Excepciones

|Excepción|Condición|
|---------------|---------------|
|<xref:System.NotSupportedException>|La secuencia que se va a convertir no admite operaciones de búsqueda.|

## <a name="remarks"></a>Comentarios

Este método de extensión solo está disponible al desarrollar aplicaciones de la Tienda Windows. Este método proporciona una forma cómoda de trabajar con secuencias en las aplicaciones de la Tienda Windows. La secuencia de .NET Framework que desea convertir debe admitir operaciones de búsqueda. Para obtener más información, vea el método <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.

> [!IMPORTANT]
> Esta API es compatible con .NET Framework 4.5.1 y versiones posteriores, pero no con la versión 4.5.

## <a name="version-information"></a>Información de versión

**.NET para aplicaciones de Windows Store**

Se admite en: Windows 8.1

## <a name="see-also"></a>Vea también

[System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)  
[Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  