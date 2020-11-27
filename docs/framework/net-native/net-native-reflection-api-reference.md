---
title: Referencia de la API de reflexión de .NET nativo
ms.date: 03/30/2017
ms.assetid: 0429c049-22a3-4ba1-9cc8-f6ee91e31d9c
ms.openlocfilehash: 4cded310397ffa4dea057899b6f008146d35a03b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250884"
---
# <a name="net-native-reflection-api-reference"></a>Referencia de la API de reflexión de .NET nativo

.NET Native incluye tres nuevos tipos de excepción: [System. Runtime. CompilerServices. MissingInteropDataException](missinginteropdataexception-class-net-native.md), [System. Reflection. MissingMetadataException](missingmetadataexception-class-net-native.md)y [System. Reflection. MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md). Tenga en cuenta lo siguiente acerca de los tres tipos de excepción:  
  
 Estos tipos son solo para uso interno.  
 Estos tres tipos de excepción son solo para el uso de la cadena de herramientas de .NET Native. Las excepciones se producen cuando la cadena de herramientas de .NET Native detecta datos que faltan y que no permite que continúe la ejecución del programa.  
  
 No debe administrar estas excepciones en su código.  
 Estas excepciones indican que los metadatos necesarios para la aplicación no están presentes (las excepciones [MissingInteropDataException](missinginteropdataexception-class-net-native.md) y [MissingMetadataException](missingmetadataexception-class-net-native.md) ) o que falta el código de implementación necesario para la aplicación (la excepción [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) ). Corrija estas condiciones de excepción mediante la modificación de un archivo de directivas de tiempo de ejecución (.rd.xml) para que el código de implementación o los metadatos necesarios estén disponibles en tiempo de ejecución. Para obtener más información, consulta [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md). Existen dos solucionadores de problemas que proporcionan las entradas adecuadas para el archivo de directivas de tiempo de ejecución que eliminará las excepciones [MissingMetadataException](missingmetadataexception-class-net-native.md) y [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) :  
  
- [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) para los tipos.  
  
- [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) para los métodos.  
  
> [!NOTE]
> Esta referencia documenta tres tipos de excepciones que son exclusivos de .NET Native. Para obtener documentación de referencia de la API de reflexión de .NET Framework Core, vea los <xref:System.Reflection> <xref:System.Reflection.Context> espacios de <xref:System.Reflection.Emit> nombres y. Para la documentación de referencia de la API de interoperabilidad de .NET Framework, consulte <xref:System.Runtime.InteropServices>.  
  
## <a name="systemreflection-namespace"></a>Espacio de nombres System.Reflection  

 El espacio de nombres <xref:System.Reflection> contiene los tipos principales utilizados para la reflexión en .NET Framework. Por .NET Native, también incluye dos nuevos tipos de excepción:  
  
|Clase|Descripción|  
|-----------|-----------------|  
|[MissingMetadataException](missingmetadataexception-class-net-native.md)|Excepción que se genera al utilizar reflexión para recuperar metadatos que no están presentes.|  
|[MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)|Excepción que se genera cuando hay disponibles metadatos para un tipo o un miembro de tipo, pero su implementación se ha quitado.|  
  
 Para obtener documentación sobre los otros tipos de este espacio de nombres, vea las páginas de referencia sobre <xref:System.Reflection> en la documentación de .NET Framework.  
  
## <a name="systemruntimecompilerservices-namespace"></a>Espacio de nombres System.Runtime.CompilerServices  

 El espacio de nombres <xref:System.Runtime.CompilerServices> incluye tipos que diseñan los compiladores de lenguaje para el usuario. Por .NET Native, también incluye un nuevo tipo de excepción:  
  
|Clase|Descripción|  
|-----------|-----------------|  
|[MissingInteropDataException](missinginteropdataexception-class-net-native.md)|Excepción que se genera cuando se llama a un método de cálculo de referencias manual, pero el análisis estático no encuentra metadatos para un tipo de análisis o no existen en un archivo de directivas en tiempo de ejecución.|  
  
 Para obtener documentación sobre los otros tipos de este espacio de nombres, vea las páginas de referencia sobre <xref:System.Runtime.CompilerServices> en la documentación de .NET Framework.  
  
## <a name="see-also"></a>Vea también

- [Clase MissingInteropDataException](missinginteropdataexception-class-net-native.md)
- [Clase MissingMetadataException](missingmetadataexception-class-net-native.md)
- [Clase MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)
- [Introducción](getting-started-with-net-native.md)
