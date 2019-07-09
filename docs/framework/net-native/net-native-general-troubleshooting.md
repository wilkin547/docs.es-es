---
title: Solución de problemas generales de .NET Native
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9599ee25e77bf6f44e5c6733deed8dc23fc0d022
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662327"
---
# <a name="net-native-general-troubleshooting"></a>Solución de problemas generales de .NET Native

Este tema describe cómo solucionar posibles problemas que pueden surgir al desarrollar aplicaciones con .NET Native.

- **Problema:** La ventana de salida de compilación no está bien actualizada.

  **Solución:** La ventana de salida de compilación no se actualiza hasta que se complete la compilación. Los tiempos de compilación pueden ser de hasta varios minutos, por lo que puede sufrir un retraso al ver las actualizaciones.

- **Problema:** Tiempo de compilación comercial de la aplicación para ARM ha aumentado.

  **Solución:** Al implementar una aplicación en el dispositivo ARM, se invoca la infraestructura de .NET Native. Esta compilación realiza un gran número de optimizaciones, además de garantizar que no sigan funcionando semánticas no estáticas como, por ejemplo, la reflexión. Asimismo, la parte de .NET Framework que la aplicación usa está vinculada estáticamente para lograr un rendimiento óptimo y debe compilarse también en código nativo. Este es el motivo por el que la compilación tarda más tiempo.

  Sin embargo, los tiempos de compilación siguen estando dentro un minuto de compilación estándar para la mayoría de las aplicaciones en un equipo de desarrollo estándar.  Normalmente, ya se tardan varios minutos solamente para generar imágenes nativas para .NET Framework en un equipo de desarrollo estándar.  Los tiempos de compilación de las aplicaciones suelen ser de un minuto o dos incluso cuando se han implementado todas las optimizaciones para mejorar el código generado e incluyendo .NET Framework.

  Seguimos trabajando para mejorar el rendimiento de compilación investigando la compilación multiproceso y otras optimizaciones.

- **Problema:** No sabe si la aplicación se ha compilado con .NET Native.

  **Solución:** Si se invoca el compilador de .NET Native, observará más tiempo de compilación y el Administrador de tareas mostrará varios procesos del componente .NET Native, como ILC.exe y nutc_driver.exe.

  Después de crear correctamente el proyecto con .NET Native, encontrará la salida en obj\\*config*\ *arch*\\*projectname*. ilc\out.  El contenido del paquete nativo final se encuentra en bin\\*arch*\\*config*\AppX. Si ha implementado la aplicación, el contenido del paquete nativo final está en \bin\\*arch*\\*config*\AppX.

- **Problema:** Su aplicación compilada con .NET Native produce excepciones en tiempo de ejecución (normalmente [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) o [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) excepciones) que no produce cuando se compila sin. NET nativo.

  **Solución:** Las excepciones se producen porque .NET Native no proporcionó los metadatos o el código de implementación en caso contrario, está disponible a través de reflexión. (para obtener más información, vea [.NET Native and Compilation](../../../docs/framework/net-native/net-native-and-compilation.md) (.NET Native y compilación)). Para eliminar la excepción, tiene que agregar una entrada a su [archivo de directivas en tiempo de ejecución (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) para que la cadena de herramientas de .NET Native pueda hacer que el código de implementación o metadatos esté disponible en tiempo de ejecución. Existen dos solucionadores de problemas que generarán la entrada necesaria para agregar al archivo de directivas en tiempo de ejecución:

  - [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) para los tipos.

  - [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) para los métodos.

  Para obtener más información, vea [Reflection and .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) (Reflexión y .NET Native).

## <a name="see-also"></a>Vea también

- [Migrar la aplicación de la Tienda Windows a .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)
