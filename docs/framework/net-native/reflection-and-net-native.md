---
title: Reflexión y .NET Native
ms.date: 03/30/2017
ms.assetid: 91c9eae4-c641-476c-a06e-d7ce39709763
ms.openlocfilehash: 65921377be9b8bf1c2d147b384c85cbd037d15f2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128187"
---
# <a name="reflection-and-net-native"></a>Reflexión y .NET Native
En .NET Framework, el desarrollo administrado admite metaprogramación a través de la API de reflexión. La reflexión permite inspeccionar los objetos en una aplicación, llamar a métodos en objetos detectados a través de la inspección, generar nuevos tipos en tiempo de ejecución y es compatible con muchos otros escenarios de código dinámico. También admite la serialización y la deserialización, lo que permite que los valores de campo de un objeto se conserven y se restauren posteriormente. Estos escenarios requieren el compilador de .NET Framework Just-in-time (JIT) para generar código nativo basado en metadatos disponibles.  
  
 El tiempo de ejecución de .NET Native no incluye un compilador JIT. Como resultado, todo el código nativo necesario debe haberse generado previamente. Se utiliza un conjunto de técnicas heurísticas para determinar qué código debe generarse, pero estas heurísticas no pueden cubrir todos los posibles escenarios de metaprogramación.  Por tanto, debe proporcionar sugerencias para estos escenarios de metaprogramación mediante [directivas de tiempo de ejecución](runtime-directives-rd-xml-configuration-file-reference.md). Si el código de metadatos o implementación necesario no está disponible en tiempo de ejecución, la aplicación inicia una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) o [MissingInteropDataException](missinginteropdataexception-class-net-native.md). Son dos los solucionadores de problemas disponibles que pueden generar la entrada adecuada para el archivo de directivas en tiempo de ejecución que elimina la excepción:  
  
- [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) para los tipos.  
  
- [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) para los métodos.  
  
> [!NOTE]
> Para obtener información general acerca del proceso de compilación de .NET Native que proporciona información general sobre por qué se necesita un archivo de directivas en tiempo de ejecución, consulte [.NET Native y compilación](net-native-and-compilation.md).  
  
 Además, .NET Native no permite reflejar sobre miembros privados de la biblioteca de clases de .NET Framework. Por ejemplo, una llamada a la propiedad <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType> para recuperar los campos de un tipo de biblioteca de clases de .NET Framework devuelve solo campos públicos o protegidos.  
  
 En los temas siguientes se proporciona información conceptual y documentación que necesita para admitir la reflexión y la serialización en sus aplicaciones:  
  
- [API basada en la reflexión](apis-that-rely-on-reflection.md)  
  
- [Referencia de la API de reflexión](net-native-reflection-api-reference.md)  
  
- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="see-also"></a>Consulte también

- [Compilar aplicaciones con .NET Native](index.md)
- [.NET Native y compilación](net-native-and-compilation.md)
