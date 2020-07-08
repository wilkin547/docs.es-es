---
title: loaderLock (MDA)
description: Revise el Asistente para la depuración administrada (MDA) de loaderLock en .NET, que detecta los intentos de ejecutar código administrado en un subproceso que contiene el bloqueo del cargador del sistema operativo Windows.
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- LoaderLock MDA
- MDAs (managed debugging assistants), loader locks
- managed debugging assistants (MDAs), loader locks
- operating system loader locks
- loader locks
- locks, threads
ms.assetid: 8c10fa02-1b9c-4be5-ab03-451d943ac1ee
ms.openlocfilehash: 055b07a805c5f0b613519d6019950a9b249a4b38
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051627"
---
# <a name="loaderlock-mda"></a>loaderLock (MDA)
El Asistente para la depuración administrada (MDA) `loaderLock` detecta los intentos de ejecutar código administrado en un subproceso que contiene el bloqueo del cargador del sistema operativo Microsoft Windows.  Cualquier ejecución de este tipo no es válida porque puede causar interbloqueos y el uso de archivos DLL antes de que se hayan inicializado por el cargador del sistema operativo.  
  
## <a name="symptoms"></a>Síntomas  
 El error más común cuando se ejecuta código dentro de un bloqueo del cargador del sistema operativo es que los subprocesos produzcan un interbloqueo al intentar llamar a otras funciones de Win32 que también requieren el bloqueo del cargador.  Ejemplos de esas funciones son `LoadLibrary`, `GetProcAddress`, `FreeLibrary` y `GetModuleHandle`.  Es posible que la aplicación no llame directamente a estas funciones; Common Language Runtime (CLR) podría llamar a estas funciones como resultado de una llamada de nivel superior como <xref:System.Reflection.Assembly.Load%2A> o la primera llamada a un método de invocación de plataforma.  
  
 También pueden producirse interbloqueos si un subproceso está esperando a que se inicie o finalice otro subproceso.  Cuando un subproceso se inicia o termina de ejecutarse, debe adquirir el bloqueo del cargador del sistema operativo para entregar eventos a los archivos DLL afectados.  
  
 Por último, hay casos donde las llamadas a archivos DLL pueden producirse antes de que el cargador del sistema operativo haya inicializado correctamente esos archivos DLL.  A diferencia de los errores de interbloqueo, que se pueden diagnosticar examinando las pilas de todos los subprocesos implicados en el interbloqueo, es muy difícil diagnosticar el uso de archivos DLL no inicializados sin usar este MDA.  
  
## <a name="cause"></a>Causa  
 Los ensamblados de C++ administrados y no administrados mixtos compilados para las versiones 1.0 o 1.1 de .NET Framework suelen intentar ejecutar código administrado dentro del bloqueo del cargador a menos que se hayan tomado precauciones especiales, por ejemplo, vinculándolos con **/NOENTRY**.
  
 Los ensamblados de C++ administrados y no administrados mixtos compilados para versión 2.0 de .NET Framework son menos susceptibles a estos problemas, y tienen el mismo riesgo reducido que las aplicaciones que usan archivos DLL no administrados que infringen las reglas del sistema operativo.  Por ejemplo, si el punto de entrada `DllMain` de un archivo DLL no administrado llama a `CoCreateInstance` para obtener un objeto administrado que se haya expuesto a COM, el resultado es un intento de ejecutar código administrado dentro del bloqueo del cargador. Para más información sobre problemas de bloqueo del cargador en la versión 2.0 y posteriores de .NET Framework, vea [Inicialización de ensamblados mixtos](/cpp/dotnet/initialization-of-mixed-assemblies).  
  
## <a name="resolution"></a>Resolución  
 En Visual C++ .NET 2002 y Visual C++ .NET 2003, los archivos DLL compilados con la opción del compilador `/clr` podían interbloquearse de forma no determinante al cargarse; esto se denominó el problema de carga de archivos DLL mixtos o bloqueo del cargador. En Visual C++ 2005 y versiones posteriores se ha quitado prácticamente toda la falta de determinación del proceso de carga de archivos DLL mixtos. En cambio, todavía hay algunos casos en los que podría producirse el bloqueo del cargador (de manera determinante). Para obtener información detallada de las causas y soluciones para el resto de los problemas de bloqueo del cargador, vea [Inicialización de ensamblados mixtos](/cpp/dotnet/initialization-of-mixed-assemblies). Si en ese tema no se identifica el problema de bloqueo del cargador, tendrá que examinar la pila del subproceso para determinar por qué se está produciendo el bloqueo del cargador y cómo corregir el problema. Examine el seguimiento de la pila para el subproceso que ha activado este MDA.  El subproceso está intentando llamar de forma no autorizada al código administrado mientras mantiene el bloqueo del cargador del sistema operativo.  Probablemente verá un punto de entrada `DllMain` o equivalente del archivo DLL en la pila.  Las reglas del sistema operativo sobre lo que se permite hacer desde dentro de este tipo de punto de entrada son bastante limitadas.  Estas reglas excluyen cualquier ejecución administrada.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Por lo general, varios subprocesos dentro del proceso producirán el interbloqueo.  Es probable que uno de esos subprocesos sea el responsable de realizar una recolección de elementos no utilizados, por lo que este interbloqueo puede tener una repercusión importante en todo el proceso.  Además, impedirá cualquier operación adicional que requiera un bloqueo del cargador del sistema operativo, como cargar y descargar ensamblados o archivos DLL, e iniciar o detener subprocesos.  
  
 En algunos casos poco frecuentes, también es posible que se desencadenen infracciones de acceso o problemas similares en los archivos DLL que se llaman antes de que se hayan inicializado.  
  
## <a name="output"></a>Output  
 Este MDA informa de que se está intentado una ejecución administrada no válida.  Tendrá que examinar la pila del subproceso para determinar por qué se está produciendo el bloqueo del cargador y cómo corregir el problema.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loaderLock/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
