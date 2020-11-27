---
title: Generar perfiles en tiempo de ejecución
description: Explore la generación de perfiles en tiempo de ejecución en .NET, que es un método para recopilar datos de rendimiento en cualquier escenario de desarrollo o implementación.
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters
- common language runtime, profiling
- Perfmon.exe
- System Monitor
- profiling
- runtime, profiling
- profiling applications
- Performance Console
ms.assetid: ccd68284-f3a8-47b8-bc3f-92e5fe3a1640
ms.openlocfilehash: 5d1542c7f6afa2d683240d6d5cca837b961eb3be
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267109"
---
# <a name="runtime-profiling"></a>Generar perfiles en tiempo de ejecución

La generación de perfiles es un método de recopilación de datos de rendimiento en cualquier escenario de desarrollo o implementación. Esta sección está dirigida a los desarrolladores y administradores del sistema que quieren recopilar información sobre el rendimiento de la aplicación.  
  
## <a name="tracking-performance-using-the-performance-monitor-perfmonexe"></a>Seguimiento del rendimiento mediante el Monitor de rendimiento (Perfmon.exe)  

 El monitor de rendimiento es la herramienta más sencilla de usar para generar perfiles de la aplicación .NET Framework. El monitor de rendimiento representa gráficamente los datos encontrados en los .NET Framework contadores de rendimiento que se instalan con el Common Language Runtime y el Windows SDK. Estos contadores se pueden usar para supervisar todo, desde la administración de la memoria hasta el rendimiento del compilador Just-In-Time (JIT). Le informan sobre los recursos que la aplicación usa, que es una medida indirecta del rendimiento de la aplicación. Use estos contadores para entender cómo funciona internamente su aplicación.  
  
#### <a name="to-run-perfmonexe-on-windows-vista-and-later-versions"></a>Para ejecutar Perfmon.exe en Windows Vista y versiones posteriores  
  
1. En el símbolo del sistema, escriba **perfmon**. Aparece la consola **Monitor de rendimiento** .  
  
2. En la carpeta **Herramientas de supervisión** , haga clic en **Monitor de rendimiento**.  
  
3. En la barra de herramientas del Monitor de rendimiento, haga clic en el icono **Agregar** (el signo más), si está presente. Si no está presente, haga clic con el botón secundario en la ventana del monitor y seleccione la opción **Agregar contadores** .  
  
     De este modo se abrirá el cuadro de diálogo **Agregar contadores** . El cuadro de lista **Contadores disponibles** muestra los objetos de rendimiento disponibles. Hay una serie de objetos predefinidos para las aplicaciones de .NET Framework, incluidos los de administración de memoria (**memoria de .NET CLR**), interoperabilidad (**interoperabilidad de .NET CLR**), control de excepciones (**excepciones de .NET CLR**) y el multithreading (**LocksAndThreads de .NET CLR**). Cada objeto de rendimiento incluye una serie de contadores de rendimiento individuales. Para obtener una lista de los contadores de rendimiento disponibles en el Monitor de rendimiento, consulte [Performance Counters](performance-counters.md).  
  
4. Active la casilla situada junto al nombre de un objeto de rendimiento para ver la lista de contadores de rendimiento individuales que admite.  
  
5. Haga clic en el contador de rendimiento que quiere ver.  
  
6. En el cuadro **de lista instancias del objeto seleccionado** , haga clic en esta opción **\<All instances>** para especificar que desea supervisar el contador de rendimiento del Common Language Runtime globalmente (es decir, en todo el sistema).  
  
     O bien  
  
     En el cuadro de lista **Instancias del objeto seleccionado** , haga clic en el nombre de una aplicación para supervisar el contador de rendimiento de dicha aplicación.  
  
     Para diferenciar varias versiones del runtime, o para eliminar la ambigüedad de varias aplicaciones con el mismo nombre, también debe modificar una clave del Registro. Para obtener más información, consulta [Performance Counters and In-Process Side-By-Side Applications](performance-counters-and-in-process-side-by-side-applications.md).  
  
> [!NOTE]
> Cuando se instalan nuevos contadores de rendimiento mientras se ejecuta la consola de rendimiento, detenga y reinicie la consola de rendimiento para que los nuevos contadores sean visibles.  
  
 Si quiere generar perfiles de un ensamblado que existe en una zona o en un recurso compartido remoto, asegúrese de que el ensamblado remoto tiene plena confianza en el equipo que ejecuta los contadores de rendimiento. Si el ensamblado no tiene suficiente confianza, los contadores de rendimiento no funcionarán. Para obtener información sobre cómo conceder confianza a distintas zonas, vea [Caspol.exe (Herramienta de la directiva de seguridad de acceso del código)](../tools/caspol-exe-code-access-security-policy-tool.md).  
  
> [!NOTE]
> En los sistemas en los que está instalado el .NET Framework 4, es posible que el monitor de rendimiento no muestre datos de contadores de rendimiento en algunas categorías, como **datos de .net CLR** y **redes de .net CLR**, para las aplicaciones desarrolladas mediante el .NET Framework 1,1. Si es así, puede configurar el monitor de rendimiento para mostrar estos datos agregando el [\<forcePerformanceCounterUniqueSharedMemoryReads>](../configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md) elemento al archivo de configuración de la aplicación.  
  
## <a name="reading-and-creating-performance-counters-programmatically"></a>Lectura y creación de contadores de rendimiento mediante programación  

 El .NET Framework proporciona clases que puede usar para tener acceso mediante programación a la misma información de rendimiento que está disponible en la consola de rendimiento. También puede usar estas clases para crear contadores de rendimiento personalizados. En la tabla siguiente se describen algunas de las clases de supervisión de rendimiento que se proporcionan en el .NET Framework.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType>|Representa un componente de contador de rendimiento de Windows NT. Use esta clase para leer contadores personalizados o predefinidos existentes y publicar datos de rendimiento (de escritura) en contadores personalizados.|  
|<xref:System.Diagnostics.PerformanceCounterCategory?displayProperty=nameWithType>|Ofrece varios métodos para interactuar con contadores y categorías de contadores en el equipo.|  
|<xref:System.Diagnostics.PerformanceCounterInstaller?displayProperty=nameWithType>|Especifica un instalador para el componente `PerformanceCounter` .|  
|<xref:System.Diagnostics.PerformanceCounterType?displayProperty=nameWithType>|Especifica la fórmula para calcular el método `NextValue` para un `PerformanceCounter`.|  
  
## <a name="see-also"></a>Vea también

- [Contadores de rendimiento](performance-counters.md)
