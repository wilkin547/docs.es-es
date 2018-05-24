---
title: Compilar aplicaciones con .NET Native
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6900bca2bd94f52ea5603c752681163cde52ce19
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
---
# <a name="compiling-apps-with-net-native"></a>Compilar aplicaciones con .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] es una tecnología de precompilación para crear e implementar aplicaciones de Windows que se incluye con Visual Studio 2015 y versiones posteriores. Su función es compilar automáticamente, a código nativo, aquellas versiones de lanzamiento de las aplicaciones escritas en código administrado (C# o Visual Basic) y que tienen como destino .NET Framework y Windows 10.  
  
 Normalmente, las aplicaciones que tienen como destino .NET Framework se compilan en lenguaje intermedio (IL). En tiempo de ejecución, el compilador Just-In-Time (JIT) convierte el IL en código nativo. Por el contrario, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compila aplicaciones de Windows directamente en código nativo. Para los desarrolladores, esto significa:  
  
-   El rendimiento del código nativo de las características de las aplicaciones. Por lo general, el rendimiento será superior al código que está en primer lugar compila IL y, a continuación, se compila a código nativo por el compilador JIT. 
  
-   Puede seguir programando en C# o Visual Basic.  
  
-   Puede continuar beneficiándose de los recursos proporcionados por .NET Framework, incluida su biblioteca de clases, la administración automática de memoria, la recolección de elementos no utilizados y el control de excepciones.  
  
 Para los usuarios de las aplicaciones, [!INCLUDE[net_native](../../../includes/net-native-md.md)] ofrece estas ventajas:  
  
-   Tiempos de ejecución más rápidos para la mayoría de las aplicaciones y escenarios.
  
-   Tiempos de inicio más rápidos para la mayoría de las aplicaciones y escenarios. 
  
-   Bajos costes de implementación y actualización.  
  
-   Optimiza el uso de memoria de la aplicación.  

> [!IMPORTANT]
> Para la mayoría de escenarios y aplicaciones, .NET Native ofrece significativamente más rápidas tiempos de inicio y un rendimiento superior en comparación con una aplicación compilada para IL o a una imagen NGEN. Sin embargo, los resultados pueden variar. Para asegurarse de que la aplicación ha beneficiado de las mejoras de rendimiento de .NET Native, se debe comparar su rendimiento con el de la versión de la aplicación no - .NET Native. Para obtener más información, consulte [información general sobre la sesión de rendimiento](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).
 
Pero [!INCLUDE[net_native](../../../includes/net-native-md.md)] implica más que una compilación en código nativo. Transforma la manera en que se compilan y ejecutan las aplicaciones de .NET Framework. En concreto:  
  
-   Durante la precompilación, las partes necesarias de .NET Framework se vinculan estáticamente en la aplicación. Esto permite que la aplicación se ejecute con bibliotecas locales de aplicación de .NET Framework y que el compilador realice un análisis global para ofrecer un gran rendimiento. Como resultado, las aplicaciones se inician sistemáticamente más rápido después de las actualizaciones de.NET Framework.  
  
-   El [!INCLUDE[net_native](../../../includes/net-native-md.md)] en tiempo de ejecución está optimizado para la precompilación estática y en la mayoría de los casos, ofrece un rendimiento superior. Al mismo tiempo, conserva las características de reflexión principales que los desarrolladores encuentran tan productivas.  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)] utiliza el mismo back-end que el compilador de C++, el cual está optimizado para escenarios de precompilación estáticos.  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] es capaz de ofrecer las ventajas de rendimiento de C++ a los desarrolladores de código administrado, ya que incorpora las mismas o parecidas herramientas que C++, como se muestra en esta tabla.  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|C++|  
|-|----------------------------------------------------------------|-----------|  
|Bibliotecas|.NET Framework + Windows en tiempo de ejecución|Win32 + Windows en tiempo de ejecución|  
|Compilador|Compilador de optimización de UTC|Compilador de optimización de UTC|  
|Implementado|Archivos binarios listos para ejecutarse|Archivos binarios listos para ejecutarse (ASM)|  
|Tiempo de ejecución|MRT.dll (tiempo de ejecución de CLR mínimo)|CRT.dll (tiempo de ejecución de C)|  
  
 Para aplicaciones de Windows 10, cargue los archivos binarios de compilación de código con .NET Native en paquetes de aplicación (archivos .appx) en la Tienda Windows.  
  
## <a name="in-this-section"></a>En esta sección  
 Para obtener más información sobre el desarrollo de aplicaciones con la compilación de código con .NET Native, vea estos temas:  
  
-   [Introducción a la compilación de código con .NET Native: tutorial de experiencia del programador](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
-   [.NET Native y compilación:](../../../docs/framework/net-native/net-native-and-compilation.md) cómo compila .NET Native el proyecto de código nativo.  
  
-   [Reflection and .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) (Reflexión y .NET Native)  
  
    -   [APIs That Rely on Reflection](../../../docs/framework/net-native/apis-that-rely-on-reflection.md) (API basadas en Reflection)  
  
    -   [Referencia de la API de reflexión](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [Serialización y metadatos](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
-   [Migrar la aplicación de la Tienda Windows a .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
-   [Solución de problemas generales de .NET Native](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
