---
title: Depurar, trazar y generar perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 855a1329c9804e4b40d796c639bbe8768156dcc2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754471"
---
# <a name="debugging-tracing-and-profiling"></a>Depurar, trazar y generar perfiles
Para depurar una aplicación de .NET Framework, el compilador y el entorno de CLR deben configurarse para poder asociar un depurador a la aplicación y para poder producir símbolos y mapas de líneas, si es posible, para la aplicación y su Lenguaje Intermedio de Microsoft (MSIL) correspondiente. Una vez depurada una aplicación administrada, se puede generar un perfil para mejorar el rendimiento. La generación de perfiles evalúa y describe las líneas de código fuente que generan el código que se ejecuta con más frecuencia, y cuánto tiempo se necesita para ejecutarlas.  
  
 Las aplicaciones de .NET Framework se depuran fácilmente con Visual Studio, que controla muchos de los detalles de la configuración. Si Visual Studio no está instalado, puede examinar y mejorar el rendimiento de las aplicaciones de .NET Framework usando las clases de depuración del espacio de nombres <xref:System.Diagnostics> de .NET Framework. Este espacio de nombres incluye las clases <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> y <xref:System.Diagnostics.TraceSource> para el seguimiento del flujo de ejecución, y las clases <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> y <xref:System.Diagnostics.PerformanceCounter> para generar perfiles de código.  
  
## <a name="in-this-section"></a>En esta sección  
 [Habilitar la depuración de adjuntos JIT](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 Muestra cómo configurar el Registro para adjuntar con JIT un motor de depuración a una aplicación de .NET Framework.  
  
 [Facilitar la depuración de una imagen](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 Muestra cómo activar el seguimiento de JIT y desactivar la optimización para facilitar la depuración de un ensamblado.  
  
 [Seguimiento e instrumentación de aplicaciones](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 Describe cómo supervisar la ejecución de la aplicación mientras se está ejecutando y cómo instrumentarla para mostrar si se ha ejecutado correctamente o si tiene errores.  
  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 Describe los asistentes para la depuración administrada (MDA), que ayudan en la depuración y trabajan con Common Language Runtime (CLR) para proporcionar información sobre el estado en tiempo de ejecución.  
  
 [Mejorar la depuración con los atributos de visualización del depurador](../../../docs/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes.md)  
 Describe el procedimiento que puede seguir el desarrollador de un tipo para especificar cómo se mostrará ese tipo en un depurador.  
  
 [Contadores de rendimiento](../../../docs/framework/debug-trace-profile/performance-counters.md)  
 Describe los contadores que puede usar para supervisar el rendimiento de una aplicación.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Depurar aplicaciones ASP.NET o ASP.NET Core en Visual Studio](/visualstudio/debugger/debugging-aspnet-and-ajax-applications)  
 Indica los requisitos previos y las instrucciones para depurar una aplicación de ASP.NET durante el desarrollo o después de la implementación.  
  
 [Guía de desarrollo](../../../docs/framework/development-guide.md)  
 Proporciona una guía para todas las áreas y tareas tecnológicas principales para el desarrollo de aplicaciones, como la creación, configuración, depuración, seguridad e implementación de la aplicación, e información sobre programación dinámica, interoperabilidad, extensibilidad, administración de memoria y subprocesamiento.
