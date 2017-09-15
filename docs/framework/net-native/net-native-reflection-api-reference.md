---
title: "Referencia de la API de reflexión de .NET nativo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0429c049-22a3-4ba1-9cc8-f6ee91e31d9c
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 695c6626c997fd8d1f034b700f4a4918eddf7db6
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="net-native-reflection-api-reference"></a>Referencia de la API de reflexión de .NET nativo
[!INCLUDE[net_native](../../../includes/net-native-md.md)] incluye tres nuevos tipos de excepción: [System.Runtime.CompilerServices.MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), [System.Reflection.MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)y [System.Reflection.MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md). Tenga en cuenta lo siguiente acerca de los tres tipos de excepción:  
  
 Estos tipos son solo para uso interno.  
 Estos tres tipos de excepción son para uso exclusivo de la cadena de herramientas de [!INCLUDE[net_native](../../../includes/net-native-md.md)] . Las excepciones se producen cuando la cadena de herramientas de [!INCLUDE[net_native](../../../includes/net-native-md.md)] detecta que faltan datos y no se puede continuar con la ejecución del programa.  
  
 No debe administrar estas excepciones en su código.  
 Estas excepciones indican que los metadatos necesarios para la aplicación no están presentes (las excepciones [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) y [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) ) o que falta el código de implementación necesario para la aplicación (la excepción [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) ). Corrija estas condiciones de excepción mediante la modificación de un archivo de directivas de tiempo de ejecución (.rd.xml) para que el código de implementación o los metadatos necesarios estén disponibles en tiempo de ejecución. Para obtener más información, consulta [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Existen dos solucionadores de problemas que proporcionan las entradas adecuadas para el archivo de directivas de tiempo de ejecución que eliminará las excepciones [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) y [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) :  
  
-   [Solucionador de problemas de MissingMetadataException](http://dotnet.github.io/native/troubleshooter/type.html) para los tipos.  
  
-   [Solucionador de problemas de MissingMetadataException](http://dotnet.github.io/native/troubleshooter/method.html) para los métodos.  
  
> [!NOTE]
>  Esta documentación hace referencia a tres tipos de excepciones que son exclusivos de [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Para obtener documentación de referencia de la API de reflexión de .NET Framework Core, consulte [Espacios de nombres System.Reflection](http://msdn.microsoft.com/library/gg145033.aspx). Para la documentación de referencia de la API de interoperabilidad de .NET Framework, consulte <xref:System.Runtime.InteropServices>.  
  
## <a name="systemreflection-namespace"></a>Espacio de nombres System.Reflection  
 El espacio de nombres <xref:System.Reflection> contiene los tipos principales utilizados para la reflexión en .NET Framework. Para [!INCLUDE[net_native](../../../includes/net-native-md.md)], también incluye dos nuevos tipos de excepción:  
  
|Clase|Descripción|  
|-----------|-----------------|  
|[MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)|Excepción que se genera al utilizar reflexión para recuperar metadatos que no están presentes.|  
|[MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)|Excepción que se genera cuando hay disponibles metadatos para un tipo o un miembro de tipo, pero su implementación se ha quitado.|  
  
 Para obtener documentación sobre los otros tipos de este espacio de nombres, vea las páginas de referencia sobre <xref:System.Reflection> en la documentación de .NET Framework.  
  
## <a name="systemruntimecompilerservices-namespace"></a>Espacio de nombres System.Runtime.CompilerServices  
 El espacio de nombres <xref:System.Runtime.CompilerServices> incluye tipos que diseñan los compiladores de lenguaje para el usuario. Para [!INCLUDE[net_native](../../../includes/net-native-md.md)], también incluye un nuevo tipo de excepción:  
  
|Clase|Descripción|  
|-----------|-----------------|  
|[MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)|Excepción que se genera cuando se llama a un método de cálculo de referencias manual, pero el análisis estático no encuentra metadatos para un tipo de análisis o no existen en un archivo de directivas en tiempo de ejecución.|  
  
 Para obtener documentación sobre los otros tipos de este espacio de nombres, vea las páginas de referencia sobre <xref:System.Runtime.CompilerServices> en la documentación de .NET Framework.  
  
## <a name="see-also"></a>Vea también  
 [Clase MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)   
 [Clase MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)   
 [Clase MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)   
 [Introducción](../../../docs/framework/net-native/getting-started-with-net-native.md)

