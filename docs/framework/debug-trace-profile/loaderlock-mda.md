---
title: "loaderLock MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "deadlocks [.NET Framework]"
  - "LoaderLock MDA"
  - "MDAs (managed debugging assistants), loader locks"
  - "managed debugging assistants (MDAs), loader locks"
  - "operating system loader locks"
  - "loader locks"
  - "locks, threads"
ms.assetid: 8c10fa02-1b9c-4be5-ab03-451d943ac1ee
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# loaderLock MDA
El asistente para la depuración administrada \(MDA\) `loaderLock` detecta intentos de ejecutar código administrado en un subproceso que contiene el bloqueo del cargador del sistema operativo Microsoft Windows.  Cualquier ejecución así no es válida porque puede causar interbloqueos y a utilizar bibliotecas DLL antes de que las haya inicializado el cargador del sistema operativo.  
  
## Síntomas  
 El error más común al ejecutar código dentro del bloqueo del cargador del sistema operativo es que los subprocesos se interbloquearán cuando se intente llamar a otras funciones de Win32 que también requieren el bloqueo del cargador.  Ejemplos de dichas funciones son `LoadLibrary`, `GetProcAddress`, `FreeLibrary` y `GetModuleHandle`.  La aplicación podría no llamar directamente a estas funciones; Common Language Runtime \(CLR\) podría llamar a estas funciones como resultado de una llamada de nivel superior como <xref:System.Reflection.Assembly.Load%2A> o la primera llamada a un método de invocación de la plataforma.  
  
 También pueden producirse interbloqueos si un subproceso está esperando a que se inicie o finalice otro subproceso.  Cuando se inicia o termina la ejecución de un subproceso, debe adquirir el bloqueo del cargador del sistema operativo para entregar los eventos a los archivos DLL afectados.  
  
 Por último, hay casos donde las llamadas a archivos DLL pueden aparecer antes de que el cargador del sistema operativo haya inicializado correctamente esos archivos DLL.  A diferencia de los errores por interbloqueo, que se pueden diagnosticar examinando las pilas de todos los subprocesos implicados en el interbloqueo, sin utilizar este MDA es muy difícil diagnosticar el uso de archivos DLL no inicializados.  
  
## Motivo  
 Los ensamblados de C\+\+ mixtos administrados\/no administrados compilados para las versiones 1.0 o 1.1 de .NET Framework suelen intentar ejecutar código administrado dentro del bloqueo del cargador a menos que se hayan tomado precauciones especiales, por ejemplo, vinculándolos con **\/NOENTRY**.  Para obtener una descripción detallada de estos problemas, vea "Mixed DLL Loading Problem" en MSDN Library.  
  
 Los ensamblados de C\+\+ mixtos administrados\/no administrados compilados para la versión 2.0 de .NET Framework son menos susceptibles a estos problemas y tienen el mismo riesgo reducido que las aplicaciones que utilizan archivos DLL no administrados que infringen las reglas del sistema operativo.  Por ejemplo, si el punto de entrada `DllMain` de una biblioteca DLL no administrada llama a `CoCreateInstance` para obtener un objeto administrado que se haya expuesto a COM, el resultado es un intento de ejecutar código administrado dentro del bloqueo del cargador.  Para obtener más información sobre los problemas de bloqueo del cargador en .NET Framework 2.0 y versiones posteriores, vea [Inicialización de ensamblados mixtos](../Topic/Initialization%20of%20Mixed%20Assemblies.md).  
  
## Resolución  
 In Visual C\+\+ .NET 2002 y Visual C\+\+ .NET 2003, los archivos DLL compilados con la opción del compilador `/clr` se podían interbloquear de manera no determinista al cargarse; este problema se conocía como carga de archivos DLL mixtos o bloqueo del cargador.  En Visual C\+\+ 2005 y versiones posteriores, se ha quitado prácticamente todo no determinismo del proceso de carga de archivos DLL mixtos.  Sin embargo, quedan algunos casos en los que se puede producir \(de manera determinista\) un bloqueo del cargador.  Para obtener información detallada sobre las causas y las soluciones de otros problemas de bloqueo del cargador, vea [Inicialización de ensamblados mixtos](../Topic/Initialization%20of%20Mixed%20Assemblies.md).  Si ese tema no incluye el problema en cuestión, examine la pila del subproceso para determinar por qué se produce el bloqueo del cargador y cómo corregir el problema.  Examine el seguimiento de la pila para conocer el subproceso que ha activado el MDA.  El subproceso está intentando llamar de manera no válida al código administrado que contiene el bloqueo del cargador del sistema operativo.  En la pila probablemente verá el punto de entrada `DllMain` de un archivo DLL o un punto de entrada equivalente.  Las reglas del sistema operativo que especifican lo que es válido hacer desde dentro de esos puntos de entrada son bastante limitadas.  Estas reglas impiden que se realice cualquier ejecución administrada.  
  
## Efecto en el Runtime  
 Normalmente, se interbloquearán varios subprocesos del proceso.  Es posible que uno de esos subprocesos sea responsable de realizar la recolección de elementos no utilizados, por lo que este interbloqueo puede tener un gran impacto en todo el proceso.  Además, impedirá cualquier operación adicional que requiera el bloqueo del cargador del sistema operativo, como cargar y descargar ensamblados o archivos DLL, e iniciar o detener subprocesos.  
  
 En algunos casos poco frecuentes, también es posible que se desencadenen infracciones de acceso o problemas parecidos en archivos DLL a los que se llama antes de que se hayan inicializado.  
  
## Resultados  
 Este MDA informa de que se está intentando realizar una ejecución administrada no válida.  Deberá examinar la pila del subproceso para determinar por qué se produce el bloqueo del cargador y cómo corregir el problema.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <loaderLock/>  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)