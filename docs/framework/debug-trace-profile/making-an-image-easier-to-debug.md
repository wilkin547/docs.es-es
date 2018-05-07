---
title: Facilitar la depuración de una imagen
ms.date: 03/30/2017
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c58008bc621ea95fbb2e4cc5e7d4521576aca37c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="making-an-image-easier-to-debug"></a>Facilitar la depuración de una imagen
Al compilar código no administrado, puede configurar una imagen ejecutable para depurarla si establece algunos modificadores IDE u opciones de línea de comandos. Por ejemplo, puede usar la opción de línea de comandos /**Zi** en Visual C++ para solicitarle que emita archivos de símbolo de depuración (con la extensión de archivo .pdb). De forma similar, la opción de línea de comandos /**Od** indica al compilador que deshabilite la optimización. El código resultante se ejecuta con mayor lentitud, pero es más fácil de depurar, en caso de que fuera necesario.  
  
 Al compilar código administrado de .NET Framework, los compiladores como Visual C++, Visual Basic y C# compilan el programa fuente en MSIL (Microsoft Intermediate Language, Lenguaje intermedio de Microsoft). Posteriormente, MSIL se compila con JIT, justo antes de ejecutarse, en código máquina nativo. Al igual que con el código no administrado, puede configurar una imagen ejecutable para depurarla si establece algunos modificadores IDE u opciones de línea de comandos. Además, la compilación JIT se puede configurar para depurar de una manera muy similar.  
  
 Esta configuración JIT tiene dos aspectos:  
  
-   Se puede solicitar al compilador JIT que genere información de seguimiento. Esto permite que el depurador empareje una cadena de MSIL con su equivalente de código administrado y realizar un seguimiento de dónde se almacenan las variables locales y los argumentos de función.  En la versión 2.0 de .NET Framework, el compilador JIT generará siempre información de seguimiento, así que no hay ninguna necesidad de solicitarla.  
  
-   Se puede solicitar al compilador JIT que no optimice el código máquina resultante.  
  
 Normalmente, el compilador que genera el MSIL establece estas opciones del compilador JIT como corresponda, en función de los modificadores de IDE u opciones de línea de comandos que se especifiquen, por ejemplo, /**Od**.  
  
 En algunos casos, puede cambiar el comportamiento del compilador JIT de forma que el código máquina que genera sea más fácil de depurar. Por ejemplo, cuando desee generar información de seguimiento JIT para una compilación comercial o la optimización de controles. Puede hacer esto con un archivo de inicialización (.ini).  
  
 Por ejemplo, si el ensamblado que desea depurar se denomina MyApp.exe, cree, en la misma carpeta que MyApp.exe, un archivo de texto denominado MyApp.ini que incluya estas tres líneas:  
  
```  
[.NET Framework Debugging Control]  
GenerateTrackingInfo=1  
AllowOptimize=0  
```  
  
 Puede establecer el valor de cada opción en 0 o 1. Cualquier opción que no se encuentre presente tiene el valor predeterminado 0. Si se establece el valor de `GenerateTrackingInfo` en 1 y el valor de `AllowOptimize` en 0, se obtiene la depuración más fácil.  
  
> [!NOTE]
>  En la versión 2.0 de .NET Framework, el compilador JIT genera siempre información de seguimiento sin tener en cuenta el valor de `GenerateTrackingInfo`; sin embargo, el valor de `AllowOptimize` sigue teniendo efecto. Al usar [Ngen.exe (generador de imágenes nativo)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) para precompilar la imagen nativa sin la optimización, el archivo .ini debe estar presente en la carpeta de destino con `AllowOptimize=0` cuando se ejecuta Ngen.exe. Si ha precompilado un ensamblado sin la optimización, debe quitar el código precompilado con la opción **/uninstall** de Ngen.exe antes de volver a ejecutar Ngen.exe para precompilar el código como optimizado. Si el archivo .ini no está presente en la carpeta, Ngen.exe precompila el código como optimizado de forma predeterminada.  
  
> [!NOTE]
>  <xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> controla los valores de un ensamblado. **DebuggableAttribute** incluye dos campos que registran la configuración que establece si el compilador JIT debe optimizar y/o generar información de seguimiento. En la versión 2.0 de .NET Framework, el compilador JIT generará siempre información de seguimiento.  
  
> [!NOTE]
>  En una compilación comercial, los compiladores no establecen ningún atributo **DebuggableAttribute**. De forma predeterminada, el compilador JIT genera el código de mayor rendimiento y más difícil de depurar. Si se habilita el seguimiento JIT, disminuye un poco el rendimiento; si se deshabilita, disminuye mucho.  
  
> [!NOTE]
>  **DebuggableAttribute** se aplica a un ensamblado completo cada vez, no a módulos individuales dentro del ensamblado. Por tanto, las herramientas de desarrollo deben asociar los atributos personalizados al token de metadatos del ensamblado, si ya se ha creado un ensamblado, o a la clase denominada **System.Runtime.CompilerServices.AssemblyAttributesGoHere**. La herramienta ALink promoverá estos atributos **DebuggableAttribute** desde cada módulo al ensamblado del que pasan a formar parte. Si hay un conflicto, la operación ALink no se realizará.  
  
> [!NOTE]
>  En el caso de la versión 1.0 de .NET Framework, el compilador de Microsoft Visual C++ agrega el atributo **DebuggableAttribute** cuando se especifican las opciones del compilador **/clr** y **/Zi**. En el caso de la versión 1.1 de .NET Framework, debe agregar manualmente en el código el atributo **DebugabbleAttribute** o usar la opción del vinculador **/ASSEMBLYDEBUG**.  
  
## <a name="see-also"></a>Vea también  
 [Depurar, trazar y generar perfiles](../../../docs/framework/debug-trace-profile/index.md)  
 [Habilitar la depuración de adjuntos JIT](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 [Habilitar la generación de perfiles](http://msdn.microsoft.com/library/3b669676-f0e0-4ebf-8674-68986dd2020d)
