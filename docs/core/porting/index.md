---
title: Portabilidad de .NET Framework a .NET Core
description: Comprenda el proceso de portabilidad y descubra herramientas que le pueden resultar útiles al realizar la portabilidad de un proyecto de .NET Framework a .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: 74fe4519e41a07bc78a4dc346f8d1b52b5c7d092
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502774"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>Introducción a la portabilidad de .NET Framework a .NET Core

Es posible que tenga código que se ejecuta actualmente en .NET Framework que le interesa portar a .NET Core. En este artículo se proporciona:

* Una introducción al proceso de portabilidad.
* Una lista de las herramientas que puede encontrar de utilidad al portar el código a .NET Core.

## <a name="overview-of-the-porting-process"></a>Introducción al proceso de portabilidad

La portabilidad a .NET Core (o .NET Standard) desde .NET Framework es relativamente sencilla para muchos proyectos. Hay una serie de cambios necesarios, pero muchos de ellos siguen los patrones descritos a continuación. Los proyectos para los que el modelo de aplicación está disponible en .NET Core (por ejemplo, bibliotecas, aplicaciones de consola y aplicaciones de escritorio) suelen requerir pocos cambios. Los proyectos que requieren un nuevo modelo de aplicación, como cuando se pasa a ASP.NET Core desde ASP.NET, requieren un poco más de trabajo, pero muchos patrones cuentan con elementos similares que se pueden usar durante la conversión. En este documento se pretende ayudar a identificar las principales estrategias que han empleado los usuarios para convertir correctamente sus bases de código para que tengan como destino .NET Standard o .NET Core. Se aborda la conversión desde dos niveles: en todo el proyecto y solo en un proyecto específico. Vea los vínculos que encontrará en la parte inferior para obtener instrucciones sobre las conversiones específicas de modelos de aplicación.

Le recomendamos que use el proceso que se indica a continuación para portar su proyecto a .NET Core. En cada uno de estos pasos, se presentan los posibles aspectos afectados por los cambios de comportamiento, por lo que debe asegurarse de probar adecuadamente la biblioteca o la aplicación antes de continuar con los pasos posteriores. Los primeros pasos consisten en preparar el proyecto para un cambio a .NET Standard o .NET Core. Si tiene pruebas unitarias, es mejor convertirlas primero para poder seguir probando los cambios en el producto en el que está trabajando. Dado que portar a .NET Core es un cambio considerable para el código base, se recomienda encarecidamente portar las proyectos de prueba de forma que se puedan ejecutar mientras porta el código. MSTest, xUnit y NUnit funcionan en .NET Core.

## <a name="getting-started"></a>Introducción

En todo el proceso se utilizarán las siguientes herramientas:

- Visual Studio 2019
- Descarga del [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md)
- Instalación _opcional_ de [dotnet try-convert](https://github.com/dotnet/try-convert)

## <a name="porting-a-solution"></a>Portabilidad de una solución

Cuando una solución contiene varios proyectos, la portabilidad puede parecer más complicada, ya que los proyectos deben abordarse en un orden específico. La conversión debe seguir un proceso con orden ascendente, en el que los proyectos sin dependencias de otros proyectos de la solución se conviertan primero y se pase a otros proyectos de la solución después.

Para identificar el orden en el que se deben migrar los proyectos, puede usar las siguientes herramientas:

- [Los diagramas de dependencia de Visual Studio](/visualstudio/modeling/create-layer-diagrams-from-your-code) pueden crear un gráfico dirigido del código en una solución.
- Ejecute `msbuild _SolutionPath_ /t:GenerateRestoreGraphFile /p:RestoreGraphOutputPath=graph.dg.json` para generar un documento JSON que incluya la lista de referencias del proyecto.
- Ejecute el [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) con el modificador `-r DGML` para recuperar un diagrama de dependencias de los ensamblados. Para más información, consulte [esta página](../../standard/analyzers/portability-analyzer.md#solution-wide-view).

Una vez que tenga la información de dependencias, puede usarla para empezar en los nodos de hoja y subir hasta el árbol de dependencias aplicando los pasos de la sección siguiente.

## <a name="per-project-steps"></a>Pasos por proyecto

Le recomendamos que use el siguiente proceso al portar un proyecto a .NET Core:

1. Convierta todas las dependencias de `packages.config` en el formato de [PackageReference](/nuget/consume-packages/package-references-in-project-files) con la [herramienta de conversión en Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).

   Este paso implica convertir las dependencias del formato `packages.config` heredado. `packages.config` no funciona en .NET Core, por lo que esta conversión es necesaria si tiene dependencias de paquete. También requiere las dependencias que está utilizando directamente en un proyecto; esto facilitará los pasos posteriores, ya que reduce la cantidad de dependencias que debe administrar.

1. Convierta el archivo de proyecto a la nueva estructura de archivos de estilo SDK. Puede crear nuevos proyectos para .NET Core y copiar los archivos de código fuente, o bien intentar convertir el archivo de proyecto existente usando una herramienta.

   .NET Core usa un [formato de archivo de proyecto](../tools/csproj.md) simplificado y diferente al de .NET Framework. Deberá convertir los archivos de proyecto en este formato para continuar. Este estilo de proyecto también le permite tener como destino .NET Framework, algo interesante en este punto.

   Puede intentar portar soluciones más pequeñas o proyectos individuales en una operación en el formato de archivo de proyecto de .NET Core con la herramienta [dotnet try-convert](https://github.com/dotnet/try-convert). No hay ninguna garantía de que `dotnet try-convert` funcione con todos los proyectos y puede provocar cambios sutiles de comportamiento de los que dependa. Use esta herramienta como _punto inicial_ que automatice los elementos básicos que se pueden automatizar. No es una solución garantizada para migrar un proyecto, ya que hay muchas diferencias en los destinos que utilizan los proyectos de estilo SDK en comparación con los archivos de proyecto de estilo antiguo.

1. Redirija todos los proyectos que quiere portar a .NET Framework 4.7.2 o versiones superiores.

   Este paso garantiza que puede usar alternativas de API para destinos específicos de .NET Framework en los casos donde .NET Core no admite una API determinada.

1. Actualice todas las dependencias a la versión más reciente. Es posible que los proyectos estén usando versiones anteriores de bibliotecas que no son compatibles con .NET Standard. Sin embargo, las versiones posteriores pueden admitirlo con un modificador simple. Esto puede requerir cambios en el código si hay cambios importantes en las bibliotecas.

1. Use el [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md) para analizar los ensamblados y ver si se pueden portar a .NET Core.

   La herramienta Analizador de portabilidad de .NET analiza los ensamblados compilados y genera un informe. Este informe muestra un resumen de portabilidad de alto nivel y un desglose de cada API que está usando y que no está disponible en NET Core. Al usar la herramienta, envíe solo el proyecto específico que quiera convertir para centrarse en los cambios de la API que puedan ser necesarios. Muchas de las API tienen una disponibilidad equivalente en .NET Core, por lo que podrá cambiar a estas.

   Al leer los informes generados por el analizador, la información importante son las API que realmente se usan, y no necesariamente el porcentaje de compatibilidad con la plataforma de destino. Muchas API tienen opciones equivalentes en .NET Standard/Core, por lo que comprender los escenarios en los que la biblioteca o la aplicación necesitan la API ayudará a determinar las consecuencias de la portabilidad.

   Hay algunos casos en los que las API no son equivalentes, por lo que deberá establecer algunas directivas de preprocesador del compilador (es decir, `#if NET45`) con el objetivo de crear casos especiales para las plataformas. En este punto, el proyecto seguirá teniendo como destino .NET Framework. Para cada uno de estos casos de destino, se recomienda utilizar condicionales conocidos que se puedan entender como un escenario.  Por ejemplo, la compatibilidad con AppDomain en .NET Core está limitada, pero, para el escenario de carga y descarga de ensamblados, hay una nueva API que no está disponible en .NET Core. Una forma común de controlar esto en el código sería como lo siguiente:

   ```csharp
   #if FEATURE_APPDOMAIN_LOADING
   // Code that uses appdomains
   #elif FEATURE_ASSEMBLY_LOAD_CONTEXT
   // Code that uses assembly load context
   #else
   #error Unsupported platform
   #endif
   ```

1. Instale el [analizador de API de .NET](../../standard/analyzers/api-analyzer.md) en los proyectos para identificar las API que inician <xref:System.PlatformNotSupportedException> en algunas plataformas y otros posibles problemas de compatibilidad.

   Esta herramienta es similar al analizador de portabilidad, pero en lugar de analizar si el código se pueden basar en .NET Core, analiza si se usa una API de forma que se inicie <xref:System.PlatformNotSupportedException> en tiempo de ejecución. Aunque esto no es habitual si va a realizar la portabilidad desde .NET Framework 4.7.2 o superior, es conveniente comprobarlo. Para obtener más información sobre las [API que generan excepciones en .NET Core](../compatibility/unsupported-apis.md), consulte el artículo.

1. En este punto, puede cambiar el destino a .NET Core (generalmente para aplicaciones) o .NET Standard (para bibliotecas).

   La elección entre .NET Core y .NET Standard depende en gran medida de dónde se ejecutará el proyecto. Si se trata de una biblioteca que usarán otras aplicaciones o se distribuirá a través de NuGet, suele elegirse .NET Standard como destino. Pero puede haber algunas API que solo estén disponibles en .NET Core por motivos de rendimiento u otras razones. En ese caso, .NET Core debe tener como destino una compilación de .NET Standard disponible, así como un rendimiento o funcionalidad reducidos. Al tener como destino .NET Standard, el proyecto estará listo para ejecutarse en nuevas plataformas (como WebAssembly). Si el proyecto tiene dependencias en marcos de aplicaciones específicos (como ASP.NET Core), el destino estará limitado por la compatibilidad de las dependencias.

   Si no hay ninguna directiva de preprocesador para el código de compilación condicional de .NET Framework o .NET Standard, bastará con encontrar lo siguiente en el archivo de proyecto:

   ```xml
   <TargetFramework>net472</TargetFramework>
   ```

   y cambiar al marco que quiera. Para .NET Core 3.1, esto sería:

   ```xml
   <TargetFramework>netcoreapp3.1</TargetFramework>
   ```

   Pero, si se trata de una biblioteca que quiere que siga siendo compatible con compilaciones específicas de .NET Framework, puede [tener varios destinos](../../standard/library-guidance/cross-platform-targeting.md); para ello, sustituya la biblioteca por lo siguiente:

   ```xml
   <TargetFrameworks>net472;netstandard2.0</TargetFrameworks>
   ```

   Si usa las API específicas de Windows (como el acceso al registro), instale el [paquete de compatibilidad con Windows](./windows-compat-pack.md).

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Análisis de dependencias](third-party-deps.md)
> [Paquete NuGet](../deploying/creating-nuget-packages.md)
> [Migración de ASP.NET a ASP.NET Core](/aspnet/core/migration/proper-to-2x)
