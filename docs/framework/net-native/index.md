---
title: Compilar aplicaciones con .NET Native
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
caps.latest.revision: 27
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 76645ae43ce6754ffdf505729ec1198785a71561
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="compiling-apps-with-net-native"></a>Compilar aplicaciones con .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] es una tecnología de precompilación para crear e implementar aplicaciones de Windows que se incluye con [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]. Su función es compilar automáticamente, a código nativo, aquellas versiones de lanzamiento de las aplicaciones escritas en código administrado (C# o Visual Basic) y que tienen como destino .NET Framework y Windows 10.  
  
 Normalmente, las aplicaciones que tienen como destino .NET Framework se compilan en lenguaje intermedio (IL). En tiempo de ejecución, el compilador Just-In-Time (JIT) convierte el IL en código nativo. Por el contrario, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compila aplicaciones de Windows directamente en código nativo. Para los desarrolladores, esto significa:  
  
-   Sus aplicaciones proporcionarán el rendimiento superior del código nativo.  
  
-   Puede seguir programando en C# o Visual Basic.  
  
-   Puede continuar beneficiándose de los recursos proporcionados por .NET Framework, incluida su biblioteca de clases, la administración automática de memoria, la recolección de elementos no utilizados y el control de excepciones.  
  
 Para los usuarios de las aplicaciones, [!INCLUDE[net_native](../../../includes/net-native-md.md)] ofrece estas ventajas:  
  
-   Tiempos de ejecución rápidos  
  
-   Tiempos de inicio rápidos y constantes  
  
-   Bajos costes de implementación y actualización  
  
-   Uso optimizado de la memoria de la aplicación  
  
 Pero [!INCLUDE[net_native](../../../includes/net-native-md.md)] implica más que una compilación en código nativo. Transforma la manera en que se compilan y ejecutan las aplicaciones de .NET Framework. En concreto:  
  
-   Durante la precompilación, las partes necesarias de .NET Framework se vinculan estáticamente en la aplicación. Esto permite que la aplicación se ejecute con bibliotecas locales de aplicación de .NET Framework y que el compilador realice un análisis global para ofrecer un gran rendimiento. Como resultado, las aplicaciones se inician sistemáticamente más rápido después de las actualizaciones de.NET Framework.  
  
-   El tiempo de ejecución de [!INCLUDE[net_native](../../../includes/net-native-md.md)] está optimizado para la precompilación estática y, por tanto, es capaz de ofrecer un rendimiento superior. Al mismo tiempo, conserva las características de reflexión principales que los desarrolladores encuentran tan productivas.  
  
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
  
-   [Reflexión y .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    -   [API basadas en la reflexión](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    -   [Referencia de la API de reflexión](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [Serialización y metadatos](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
-   [Migrar la aplicación de la Tienda Windows a .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
-   [Solución de problemas generales de .NET Native](../../../docs/framework/net-native/net-native-general-troubleshooting.md)  
  
## <a name="see-also"></a>Vea también  
 [Preguntas más frecuentes acerca de .NET Native](http://msdn.microsoft.com/vstudio/dn642499.aspx)

