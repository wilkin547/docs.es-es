---
title: Identificación de la secuencia de proyectos que se van a migrar
description: Normalmente, las aplicaciones de gran tamaño no se migran a las nuevas plataformas a la vez, sino que en una serie de pasos más pequeños. Obtenga información sobre cómo planear los pasos para migrar una aplicación ASP.NET MVC a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 452898da5839f8979a5e4f9ebf5d4c21b250e1fa
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401764"
---
# <a name="identify-sequence-of-projects-to-migrate"></a>Identificación de la secuencia de proyectos que se van a migrar

En el caso de las soluciones que implican varias aplicaciones front-end, es mejor migrar las aplicaciones una por una. Por ejemplo, cree una solución que solo incluya una aplicación front-end y sus dependencias para que pueda identificar fácilmente el ámbito de trabajo implicado. Las soluciones son ligeras y puede incluir proyectos en varias soluciones si es necesario. Aproveche las ventajas de las soluciones como una herramienta organizativa al migrar.

Una vez que haya identificado la aplicación ASP.NET que se va a migrar y que sus proyectos dependientes se encuentren con él (idealmente en una solución), el paso siguiente consiste en identificar las dependencias de .NET Framework y NuGet. Una vez identificadas todas las dependencias, el enfoque más sencillo de migración es un enfoque "inferior". Con este enfoque, el nivel más bajo de dependencias se migra primero. A continuación, se migra el siguiente nivel de dependencias, hasta que, hasta el momento, lo único que queda es la aplicación de front-end. En la figura 3-1 se muestra un conjunto de proyectos de ejemplo de creación de una aplicación. Las bibliotecas de clases de bajo nivel se encuentran en la parte inferior y el proyecto ASP.NET MVC está en la parte superior.

![Dependencias del proyecto](./media/Figure3-1.png)

**Figura 3-1.** Gráfico de dependencias del proyecto.

Elija una aplicación de front-end determinada, un proyecto de ASP.NET MVC 5/Web API 2. Identifique sus dependencias en la solución y asigne sus dependencias hasta que tenga una lista completa. Un diagrama como el que se muestra en la figura 3-1 puede ser útil al asignar las dependencias del proyecto. Visual Studio puede generar un [Diagrama de dependencias para la solución](/visualstudio/modeling/create-layer-diagrams-from-your-code), en función de la edición que esté usando. [El analizador de portabilidad de .net](../../standard/analyzers/portability-analyzer.md) también puede generar diagramas de dependencia.

En la figura 3-2 se muestra el instalador de la [extensión de Visual Studio del analizador de portabilidad de .net](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer):

![Instalar la extensión del analizador de portabilidad de .NET](./media/Figure3-2.png)

**Figura 3-2.** Instalador del analizador de portabilidad de .NET.

La extensión es compatible con Visual Studio 2017 y versiones posteriores. Una vez instalado, configúrelo en el menú de configuración **analizar** el  >  **analizador de portabilidad** , como se muestra en la figura 3-3.

![Configurar la extensión del analizador de portabilidad de .NET](./media/Figure3-3.png)

**Figura 3-3.** Configure el analizador de portabilidad de .NET.

El analizador genera un informe detallado para cada ensamblado. El informe:

* Describe cómo es compatible cada proyecto con un marco de trabajo de destino determinado, como .NET Core 3,1 o .NET Standard 2,0.
* Ayuda a los equipos a evaluar el esfuerzo necesario para trasladar un proyecto determinado a un marco de trabajo de destino determinado.

Los detalles de este análisis se describen en la sección siguiente.

Una vez que haya asignado los proyectos y sus relaciones entre sí, estará listo para determinar el orden en el que va a migrar los proyectos. Comienza con proyectos que no tienen dependencias. A continuación, trabaje hasta el árbol para los proyectos que dependen de estos proyectos.

En el ejemplo que se muestra en la figura 3-1, comenzaría con el proyecto *contoso. utils* , ya que no depende de ningún otro proyecto. A continuación, *contoso. Data* , ya que solo depende de "utils". Después, migre la biblioteca "ensamblado BusinessLogic" y, por último, el proyecto de ASP.NET "Web" de front-end. Seguir este enfoque "de abajo arriba" funciona bien para aplicaciones relativamente pequeñas y bien factorizadas que se pueden migrar como una unidad una vez que se han migrado todos sus proyectos. Las aplicaciones más grandes con más complejidad, o más código que tardará más tiempo en migrarse, pueden tener que considerar estrategias más incrementales.

## <a name="unit-tests"></a>Pruebas unitarias

Missing en los diagramas anteriores son proyectos de prueba unitaria. Espero que haya pruebas que cubran al menos parte del comportamiento existente de las bibliotecas que se van a trasladar.

Si tiene pruebas unitarias, es mejor convertir primero esos proyectos. Querrá seguir probando los cambios en el proyecto en el que está trabajando. Recuerde que la migración a .NET Core es un cambio significativo en el código base.

MSTest, xUnit y NUnit funcionan en .NET Core. Si actualmente no tiene pruebas para la aplicación, considere la posibilidad de crear algunas pruebas de caracterización que comprueben el comportamiento actual del sistema. La ventaja es que una vez completada la migración, puede confirmar que el comportamiento de la aplicación permanece inalterado.

## <a name="considerations-for-migrating-many-apps"></a>Consideraciones para la migración de muchas aplicaciones

Algunas organizaciones tendrán muchas aplicaciones diferentes para migrar, y la migración de cada una de ellas puede requerir que se tenable demasiados recursos. En estas situaciones, se recomienda cierto grado de automatización. Los pasos que se siguen en este capítulo se pueden automatizar. Los cambios estructurales, como las diferencias en los archivos de proyecto y las actualizaciones de los paquetes comunes, pueden aplicarse mediante scripts. Estos scripts se pueden refinar a medida que se ejecutan de forma iterativa en más proyectos. En cada ejecución, examine los pasos manuales necesarios para cada proyecto. Si es posible, automatice los pasos manuales. Con este enfoque, la organización debe crecer más rápido y mejor a la hora de migrar sus aplicaciones a lo largo del tiempo, con una mejor automatización compatible con cada paso del proceso.

Vea información general sobre cómo emplear este enfoque en esta [presentación de dotNetConf de Lizzy Gallagher de MasterCard](https://www.youtube.com/watch?v=C-2haqb60No). Las cinco fases empleadas en esta presentación incluyen:

- Migración de dependencias de NuGet de terceros
- Migración de aplicaciones para usar el nuevo formato de archivo *. csproj*
- Migración de aplicaciones a ASP.NET Core (con .NET Framework de destino)
- Actualización de las dependencias de NuGet internas en .NET Standard
- Actualice todas las aplicaciones para que tengan como destino .NET Core 3,1

Al automatizar un gran conjunto de aplicaciones, ayuda significativamente si siguen las directrices de codificación coherentes y la organización del proyecto. Los esfuerzos de automatización se basan en esta coherencia para ser eficaces. Además de analizar y migrar archivos de proyecto, los patrones de código comunes se pueden migrar automáticamente. Algunos ejemplos de patrones de código incluyen diferencias en cómo se declaran las acciones de controlador o cómo devuelven resultados.

Por ejemplo, un script de migración podría buscar archivos que coincidan con *Controller.CS* para las líneas de código que coinciden con uno de estos patrones:

```csharp
   return new HttpStatusCodeResult(200);
   // or
   return new HttpStatusCodeResult(HttpStatusCode.OK);
```

En ASP.NET Core, cualquiera de las líneas de código anteriores se puede reemplazar por:

```csharp
    return Ok();
```

## <a name="summary"></a>Resumen

El mejor método para migrar una aplicación de .NET Framework grande a .NET Core es:

1. Identifique las dependencias del proyecto.
1. Analice lo que se necesita para portar cada proyecto.
1. Empiece en orden ascendente.

Puede usar el analizador de portabilidad de .NET para determinar cómo pueden estar las bibliotecas existentes compatibles con las plataformas de destino. Las pruebas automatizadas ayudarán a garantizar que no se introducen cambios importantes a medida que se traslada la aplicación. Estos proyectos de prueba deben estar entre los primeros proyectos migrados.

## <a name="references"></a>Referencias

- [Portabilidad de .NET Framework a .NET Core](../../core/porting/index.md)
- [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md)
- [Channel 9: un breve vistazo al analizador de portabilidad de .NET (vídeo)](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer)
- [2 años, 200 aplicaciones: una migración de .NET Core a escala (vídeo)](https://www.youtube.com/watch?v=C-2haqb60No)

>[!div class="step-by-step"]
>[Anterior](migrate-large-solutions.md)
>[Siguiente](understand-update-dependencies.md)
