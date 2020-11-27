---
title: Depurar, trazar y generar perfiles
description: Obtenga información sobre la depuración, el seguimiento y la generación de perfiles en .NET. Consulte los artículos que abarcan las aplicaciones de depuración Just-in-Time (JIT), seguimiento e instrumentación, etc.
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
ms.openlocfilehash: 33dd840f4c1421bbff54499af56ab3e147cc694b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272779"
---
# <a name="debugging-tracing-and-profiling"></a>Depurar, trazar y generar perfiles

Para depurar una aplicación de .NET Framework, el compilador y el entorno de CLR deben configurarse para poder asociar un depurador a la aplicación y para poder producir símbolos y mapas de líneas, si es posible, para la aplicación y su Lenguaje Intermedio de Microsoft (MSIL) correspondiente. Una vez depurada una aplicación administrada, se puede generar un perfil para mejorar el rendimiento. La generación de perfiles evalúa y describe las líneas de código fuente que generan el código que se ejecuta con más frecuencia, y cuánto tiempo se necesita para ejecutarlas.  
  
 Las aplicaciones de .NET Framework se depuran fácilmente con Visual Studio, que controla muchos de los detalles de la configuración. Si Visual Studio no está instalado, puede examinar y mejorar el rendimiento de las aplicaciones de .NET Framework usando las clases de depuración del espacio de nombres <xref:System.Diagnostics> de .NET Framework. Este espacio de nombres incluye las clases <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> y <xref:System.Diagnostics.TraceSource> para el seguimiento del flujo de ejecución, y las clases <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> y <xref:System.Diagnostics.PerformanceCounter> para generar perfiles de código.  
  
## <a name="in-this-section"></a>En esta sección  

 [Habilitar la depuración de adjuntos JIT](enabling-jit-attach-debugging.md)  
 Muestra cómo configurar el Registro para adjuntar con JIT un motor de depuración a una aplicación de .NET Framework.  
  
 [Facilitar la depuración de una imagen](making-an-image-easier-to-debug.md)  
 Muestra cómo activar el seguimiento de JIT y desactivar la optimización para facilitar la depuración de un ensamblado.  
  
 [Seguimiento e instrumentación de aplicaciones](tracing-and-instrumenting-applications.md)  
 Describe cómo supervisar la ejecución de la aplicación mientras se está ejecutando y cómo instrumentarla para mostrar si se ha ejecutado correctamente o si tiene errores.  
  
 [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)  
 Describe los asistentes para la depuración administrada (MDA), que ayudan en la depuración y trabajan con Common Language Runtime (CLR) para proporcionar información sobre el estado en tiempo de ejecución.  
  
 [Mejorar la depuración con los atributos de visualización del depurador](enhancing-debugging-with-the-debugger-display-attributes.md)  
 Describe el procedimiento que puede seguir el desarrollador de un tipo para especificar cómo se mostrará ese tipo en un depurador.  
  
 [Contadores de rendimiento](performance-counters.md)  
 Describe los contadores que puede usar para supervisar el rendimiento de una aplicación.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Depuración de aplicaciones de ASP.NET o ASP.NET Core en Visual Studio](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)  
 Indica los requisitos previos y las instrucciones para depurar una aplicación de ASP.NET durante el desarrollo o después de la implementación.  
  
 [Guía de desarrollo para .NET Framework](../development-guide.md)  
 Proporciona una guía para todas las áreas y tareas tecnológicas principales para el desarrollo de aplicaciones, como la creación, configuración, depuración, seguridad e implementación de la aplicación, e información sobre programación dinámica, interoperabilidad, extensibilidad, administración de memoria y subprocesamiento.
