---
title: Excepciones de tiempo de ejecución en las aplicaciones nativas de .NET
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
ms.openlocfilehash: 12df2ef7bf6e86a60dfa4c130f35969e72ac5211
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180950"
---
# <a name="runtime-exceptions-in-net-native-apps"></a>Excepciones de tiempo de ejecución en las aplicaciones nativas de .NET
Es importante probar las versiones de lanzamiento de la aplicación de la Plataforma universal de Windows en las plataformas de destino, ya que las configuraciones de depuración y de lanzamiento son completamente diferentes. De forma predeterminada, la configuración de depuración utiliza el tiempo de ejecución de .NET Core para compilar la aplicación, pero la configuración de lanzamiento usa .NET Native para compilar la aplicación en código nativo.  
  
> [!IMPORTANT]
> Para obtener información sobre cómo tratar con las excepciones [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md)y [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) que puede encontrar al probar las versiones de lanzamiento de la aplicación, vea "Paso 4: resolver manualmente los metadatos que faltan: en el tema [Introducción,](getting-started-with-net-native.md) así como Referencia del archivo de configuración de [Reflection y .NET Native](reflection-and-net-native.md) y Runtime [Directives (rd.xml).](runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="debug-and-release-builds"></a>Compilaciones de depuración y de lanzamiento  
 Cuando se ejecuta la compilación de depuración en el tiempo de ejecución de .NET Core, no se ha compilado en código nativo. Esto hace que todos los servicios que normalmente ofrece el tiempo de ejecución estén disponibles para su aplicación.  
  
 Por otro lado, la compilación de lanzamiento compila a código nativo para las plataformas de destino, quita la mayoría de dependencias de bibliotecas y tiempos de ejecución externos y optimiza enormemente el código para obtener el máximo rendimiento.  
  
 Cuando se depuran compilaciones de lanzamiento que se compilaron con .NET Native:  
  
- Use el motor de depuración de .NET Native, que es diferente de las herramientas de depuración de .NET normal.  
  
- El tamaño de su archivo ejecutable se reduce tanto como sea posible. Una de las formas en que .NET Native reduce el tamaño de un archivo ejecutable es recortando considerablemente los mensajes de excepción en tiempo de ejecución, un tema que se explica con más detalle en la sección [Runtime exception messages](#Messages) .  
  
- El código está altamente optimizado. Esto significa que la inserción se utiliza siempre que es posible. (La inserción mueve el código de las rutinas externas a la rutina de llamada.)   El hecho de que .NET Native proporciona un tiempo de ejecución especializado e implementa una inserción agresiva afecta a la pila de llamadas que se muestra al depurar.  Para más información, consulte la sección [Runtime call stack](#CallStack) .  
  
> [!NOTE]
> Puede controlar si las compilaciones de depuración y de lanzamiento se compilan con la cadena de herramientas de .NET Native mediante la activación o desactivación del cuadro **Compilar con cadena de herramientas de .NET Native** .   Sin embargo, tenga en cuenta que la Tienda Windows siempre compilará la versión de producción de la aplicación con la cadena de herramientas de .NET Native.  
  
<a name="Messages"></a>
## <a name="runtime-exception-messages"></a>Runtime exception messages  
 Para minimizar el tamaño del archivo ejecutable de la aplicación, .NET Native no incluye el texto completo de los mensajes de excepción. Como resultado, puede que las excepciones de tiempo de ejecución en las compilaciones de lanzamiento no muestren el texto completo de los mensajes de excepción. En su lugar, el texto puede constar de una subcadena junto con un vínculo para obtener más información. Por ejemplo, la información de excepción puede aparecer como:  
  
```output
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 Si necesita el mensaje de excepción completo, ejecute en su lugar la versión de depuración. Por ejemplo, la información de excepción anterior de la compilación de lanzamiento puede aparecer en la compilación de depuración como se indica a continuación:  
  
```output
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>
## <a name="runtime-call-stack"></a>Runtime call stack  
 Debido a la inserción y a otras optimizaciones, puede que la pila de llamadas que muestra una aplicación compilada con la cadena de herramientas de .NET Native no le ayude a identificar claramente la ruta de acceso a una excepción en tiempo de ejecución.  
  
 Para obtener la pila completa, ejecute la compilación de depuración en su lugar.  
  
## <a name="see-also"></a>Consulte también

- [Depuración de aplicaciones universales de Windows de .NET Native](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [Introducción](getting-started-with-net-native.md)
