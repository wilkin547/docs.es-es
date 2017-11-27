---
title: "Reflexión y .NET Native"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c9eae4-c641-476c-a06e-d7ce39709763
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9e4bdc26815feab7910e7518f7cd691a1f4dece
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="reflection-and-net-native"></a>Reflexión y .NET Native
En .NET Framework, el desarrollo administrado admite metaprogramación a través de la API de reflexión. La reflexión permite inspeccionar los objetos en una aplicación, llamar a métodos en objetos detectados a través de la inspección, generar nuevos tipos en tiempo de ejecución y es compatible con muchos otros escenarios de código dinámico. También admite la serialización y la deserialización, lo que permite que los valores de campo de un objeto se conserven y se restauren posteriormente. Estos escenarios requieren el compilador de .NET Framework Just-in-time (JIT) para generar código nativo basado en metadatos disponibles.  
  
 El tiempo de ejecución de [!INCLUDE[net_native](../../../includes/net-native-md.md)] no incluye un compilador JIT. Como resultado, todo el código nativo necesario debe haberse generado previamente. Se utiliza un conjunto de técnicas heurísticas para determinar qué código debe generarse, pero estas heurísticas no pueden cubrir todos los posibles escenarios de metaprogramación.  Por tanto, debe proporcionar sugerencias para estos escenarios de metaprogramación mediante [directivas de tiempo de ejecución](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Si el código de metadatos o implementación necesario no está disponible en tiempo de ejecución, la aplicación inicia una excepción [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) o [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md). Son dos los solucionadores de problemas disponibles que pueden generar la entrada adecuada para el archivo de directivas en tiempo de ejecución que elimina la excepción:  
  
-   [Solucionador de problemas de MissingMetadataException](http://dotnet.github.io/native/troubleshooter/type.html) para los tipos.  
  
-   [Solucionador de problemas de MissingMetadataException](http://dotnet.github.io/native/troubleshooter/method.html) para los métodos.  
  
> [!NOTE]
>  Para obtener información general acerca del proceso de compilación de .NET Native que proporciona información general sobre por qué se necesita un archivo de directivas en tiempo de ejecución, consulte [.NET Native y compilación](../../../docs/framework/net-native/net-native-and-compilation.md).  
  
 Además, [!INCLUDE[net_native](../../../includes/net-native-md.md)] no le permite reflejar en los miembros privados de la biblioteca de clases de .NET Framework. Por ejemplo, una llamada a la propiedad <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType> para recuperar los campos de un tipo de biblioteca de clases de .NET Framework devuelve solo campos públicos o protegidos.  
  
 En los temas siguientes se proporciona información conceptual y documentación que necesita para admitir la reflexión y la serialización en sus aplicaciones:  
  
-   [APIs That Rely on Reflection](../../../docs/framework/net-native/apis-that-rely-on-reflection.md) (API basadas en Reflection)  
  
-   [Referencia de la API de reflexión](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
-   [Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="see-also"></a>Vea también  
 [Compilar aplicaciones con .NET Native](../../../docs/framework/net-native/index.md)  
 [.NET Native and Compilation](../../../docs/framework/net-native/net-native-and-compilation.md) (.NET Native y compilación)
