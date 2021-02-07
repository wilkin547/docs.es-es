---
description: 'Más información acerca de: .NET Native solución de problemas generales'
title: Solución de problemas generales de .NET Native
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
ms.openlocfilehash: c486b1968036c42ac6d6e565abd9a9f7d795abc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738538"
---
# <a name="net-native-general-troubleshooting"></a>Solución de problemas generales de .NET Native

En este tema se describe cómo solucionar los posibles problemas que pueden surgir al desarrollar aplicaciones con .NET Native.

- **Problema:** la ventana de salida de compilación no está bien actualizada.

  **Solución:** la ventana de salida de compilación no se actualiza hasta que la compilación haya finalizado. Los tiempos de compilación pueden ser de hasta varios minutos, por lo que puede sufrir un retraso al ver las actualizaciones.

- **Problema:** el tiempo de compilación comercial de la aplicación para ARM ha aumentado.

  **Solución:** Cuando se implementa una aplicación en el dispositivo ARM, se invoca la infraestructura de .NET Native. Esta compilación realiza un gran número de optimizaciones, además de garantizar que no sigan funcionando semánticas no estáticas como, por ejemplo, la reflexión. Asimismo, la parte de .NET Framework que la aplicación usa está vinculada estáticamente para lograr un rendimiento óptimo y debe compilarse también en código nativo. Este es el motivo por el que la compilación tarda más tiempo.

  Sin embargo, los tiempos de compilación siguen estando dentro un minuto de compilación estándar para la mayoría de las aplicaciones en un equipo de desarrollo estándar.  Normalmente, ya se tardan varios minutos solamente para generar imágenes nativas para .NET Framework en un equipo de desarrollo estándar.  Los tiempos de compilación de las aplicaciones suelen ser de un minuto o dos incluso cuando se han implementado todas las optimizaciones para mejorar el código generado e incluyendo .NET Framework.

  Seguimos trabajando para mejorar el rendimiento de compilación investigando la compilación multiproceso y otras optimizaciones.

- **Problema:** No sabe si la aplicación se compiló mediante .NET Native.

  **Solución:** Si se invoca el compilador de .NET Native, observará que los tiempos de compilación son más prolongados y que el administrador de tareas mostrará diversos procesos de componentes de .NET Native como ILC.exe y nutc_driver.exe.

  Después de compilar correctamente el proyecto con .net Native, encontrará la salida en la \\ *configuración* de obj \  *Arch* \\ . ilc\out.  El contenido del paquete nativo final se encuentra en bin \\ *Arch* \\ *config*\AppX. El contenido del paquete nativo final está en \Bin \\ *Arch* \\ *config*\appx. Si ha implementado la aplicación.

- **Problema:** su aplicación compilada con .NET Native produce excepciones en tiempo de ejecución (normalmente excepciones [MissingMetadataException](missingmetadataexception-class-net-native.md) o [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)) que no produjo al compilarse sin .NET Native.

  **Solución:** las excepciones se producen porque .NET Native no ha proporcionado los metadatos o el código de implementación, que en otras circunstancias están disponibles a través de reflexión (Para obtener más información, vea [.net Native y compilación](net-native-and-compilation.md)). Para eliminar la excepción, tiene que agregar una entrada al archivo de [directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md) para que la cadena de herramientas de .net Native pueda hacer que el código de implementación o metadatos esté disponible en tiempo de ejecución. Existen dos solucionadores de problemas que generarán la entrada necesaria para agregar al archivo de directivas en tiempo de ejecución:

  - [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) para los tipos.

  - [Solucionador de problemas de MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) para los métodos.

  Para obtener más información, vea [Reflection and .NET Native](reflection-and-net-native.md) (Reflexión y .NET Native).

## <a name="see-also"></a>Vea también

- [Migrar la aplicación de la Tienda Windows a .NET Native](migrating-your-windows-store-app-to-net-native.md)
