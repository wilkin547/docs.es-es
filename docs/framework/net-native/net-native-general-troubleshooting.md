---
title: "Soluci&#243;n de problemas generales de .NET Native | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Soluci&#243;n de problemas generales de .NET Native
En este tema se describe cómo solucionar posibles problemas que pueden surgir al desarrollar de aplicaciones con [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
-   **Problema:** la ventana de resultados de compilación no está bien actualizada.  
  
     **Solución:** la ventana de resultados de compilación no se actualiza hasta que la compilación haya finalizado.  Los tiempos de compilación pueden ser de hasta varios minutos, por lo que puede sufrir un retraso al ver las actualizaciones.  
  
-   **Problema:** el tiempo de compilación comercial de la aplicación para ARM ha aumentado.  
  
     **Solución:** cuando se implementa una aplicación en un dispositivo ARM, se invoca la infraestructura de [!INCLUDE[net_native](../../../includes/net-native-md.md)].  Esta compilación realiza un gran número de optimizaciones, además de garantizar que no sigan funcionando semánticas no estáticas como, por ejemplo, la reflexión.  Asimismo, la parte de .NET Framework que la aplicación usa está vinculada estáticamente para lograr un rendimiento óptimo y debe compilarse también en código nativo.  Este es el motivo por el que la compilación tarda más tiempo.  
  
     Sin embargo, los tiempos de compilación siguen estando dentro un minuto de compilación estándar para la mayoría de las aplicaciones en un equipo de desarrollo estándar.  Normalmente, ya se tardan varios minutos solamente para generar imágenes nativas para .NET Framework en un equipo de desarrollo estándar.  Los tiempos de compilación de las aplicaciones suelen ser de un minuto o dos incluso cuando se han implementado todas las optimizaciones para mejorar el código generado e incluyendo .NET Framework.  
  
     Seguimos trabajando para mejorar el rendimiento de compilación investigando la compilación multiproceso y otras optimizaciones.  
  
-   **Problema:** no sabe si su aplicación se compiló con [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
     **Solución:** si el compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] se invoca, notará que los tiempos de compilación son más prolongados y que el Administrador de tareas muestra varios procesos del componente [!INCLUDE[net_native](../../../includes/net-native-md.md)], como ILC.exe y nutc\_driver.exe.  
  
     Cuando termine de compilar el proyecto correctamente con [!INCLUDE[net_native](../../../includes/net-native-md.md)], verá el resultado en obj\\*config*\\ *arch*\\*projectname*.ilc\\out.  El contenido del paquete nativo final se encuentra en bin\\*arc*\\*config*\\AppX.  Si ha implementado la aplicación, el contenido del paquete nativo final está en \\bin\\*arch*\\*config*\\AppX.  
  
-   **Problema:** Su aplicación compilada con .NET Native produce excepciones en tiempo de ejecución \(normalmente excepciones [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) o [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)\) que no produjo cuando compiló sin .NET Native.  
  
     **Resolución:** Las excepciones se producen porque .NET Native no proporcionó los metadatos o el código de implementación que, en caso contrario, está disponible a través de reflexión  \(para obtener más información, consulte [.NET Native y compilación](../../../docs/framework/net-native/net-native-and-compilation.md)\). Para eliminar la excepción, tiene que agregar una entrada a su [archivo de directivas \(rd.xml\) en tiempo de ejecución](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) para que la cadena de herramientas de .NET Native pueda hacer que el código de implementación o metadatos esté disponible en tiempo de ejecución.  Existen dos solucionadores de problemas que generarán la entrada necesaria para agregar al archivo de directivas en tiempo de ejecución:  
  
    -   [Solucionador de problemas MissingMetadataException](http://dotnet.github.io/native/troubleshooter/type.html)para los tipos.  
  
    -   [Solucionador de problemas MissingMetadataException](http://dotnet.github.io/native/troubleshooter/method.html)para los métodos.  
  
     Para obtener más información, consulte [Reflexión y .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md).  
  
## Vea también  
 [Migrar la aplicación de la Tienda Windows a .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)