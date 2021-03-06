---
title: Descripción y actualización de dependencias
description: Para migrar un proyecto de .NET Framework a .NET Core, sus dependencias deben actualizarse para que funcionen con .NET Core. En esta sección se examinan las herramientas y los enfoques que se pueden usar para planear las migraciones de aplicaciones de gran tamaño.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: afad77860099e4737b5270dc32fc20c2025e63dd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401686"
---
# <a name="understand-and-update-dependencies"></a>Descripción y actualización de dependencias

Después de identificar la secuencia en la que se deben migrar los proyectos individuales de la aplicación, el siguiente paso es comprender las dependencias de cada proyecto y actualizarlas si es necesario. En el caso de las dependencias de plataforma, la mejor manera de empezar es ejecutar el [analizador de portabilidad de .net](../../standard/analyzers/portability-analyzer.md) en el ensamblado en cuestión y, a continuación, examinar los resultados detallados que se generan. La herramienta se configura para especificar una o varias plataformas de destino, como .NET Core 3,1 o .NET Standard 2,0. Los resultados se proporcionan con los detalles de cada plataforma de destino. En la figura 3-4 se muestra un ejemplo de la salida de la herramienta.

![Detalles del informe del analizador de portabilidad de .NET](./media/Figure3-4.png)

**Figura 3-4.** Detalles del informe del analizador de portabilidad de .NET.

## <a name="update-class-library-dependencies"></a>Actualizar las dependencias de la biblioteca de clases

Las aplicaciones de gran tamaño normalmente implican varios proyectos, y la mayoría de los proyectos distintos del proyecto Web de MVC de ASP.NET son probablemente bibliotecas de clases. Las bibliotecas de clases suelen ser el puerto más sencillo entre las plataformas de .NET, especialmente en comparación con los proyectos de ASP.NET, que son entre las más difíciles (y que normalmente deben volver a crearse).

Los equipos pueden considerar la [herramienta de prueba de conversión](https://github.com/dotnet/try-convert) o la [herramienta del Asistente para actualización de .net](https://aka.ms/dotnet-upgrade-assistant) para migrar bibliotecas de clases a .net Core. Estas herramientas analizan un archivo de proyecto de .NET Framework e intentan migrarlo al formato de archivo de proyecto de .NET Core, lo que realiza las modificaciones que puede realizar con seguridad en el proceso. Las herramientas pueden requerir cierta asistencia manual para trabajar con proyectos de ASP.NET, pero normalmente pueden ayudar a acelerar el proceso de migración de bibliotecas de clases.

Las herramientas de prueba de actualización y del Asistente para actualización se implementan como herramientas de línea de comandos de .NET Core. Solo se ejecutan en Windows, ya que están diseñados para funcionar con .NET Framework aplicaciones. Puede instalar try-Convert ejecutando el comando siguiente desde un símbolo del sistema:

```dotnetcli
dotnet tool install -g try-convert
```

Una vez que haya instalado correctamente la herramienta, puede ejecutar `try-convert` en la carpeta donde se encuentra el archivo de proyecto de la biblioteca de clases.

Instale el Asistente para actualización de .NET con el siguiente comando (después de instalar try-Convert):

```dotnetcli
dotnet tool install -g upgrade-assistant
```

Ejecute la herramienta con el comando `upgrade-assistant <project>` en la carpeta donde se encuentra el archivo de proyecto.

## <a name="update-nuget-package-dependencies"></a>Actualización de las dependencias de paquetes NuGet

Analice el uso de paquetes de NuGet de terceros y determine si alguno de ellos todavía no admite .NET Standard (o no lo admite pero solo con una versión nueva). Puede ser útil [actualizar paquetes NuGet para usar `<PackageReference>` la sintaxis con la herramienta de conversión de Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference), de modo que las dependencias de nivel superior estén visibles. A continuación, compruebe si las versiones actuales o posteriores de estos paquetes son compatibles con .NET Core o .NET Standard. Esta información puede encontrarse en [nuget.org] o en Visual Studio para cada paquete.

Si existe compatibilidad con la versión del paquete que usa la aplicación actualmente, ¡ genial! Si no es así, consulte si hay una versión más reciente del paquete que tenga soporte técnico e investigue lo que sería necesario para la actualización. Puede haber cambios importantes en el paquete, especialmente si la versión principal del paquete cambia entre la versión usada actualmente y la que está actualizando.

En algunos casos, ninguna versión de un paquete determinado funciona con .NET Core. En ese caso, los equipos tienen un par de opciones. Pueden continuar dependiendo de la versión de .NET Framework, pero esto tiene limitaciones. La aplicación solo se ejecutará en Windows y es posible que el equipo desee ejecutar el analizador de portabilidad en los archivos binarios del paquete para ver si hay algún problema que pueda encontrar. Ciertamente, el equipo querrá probar exhaustivamente. La otra opción es buscar un paquete diferente o, si el paquete necesario es de código abierto, actualizarlo a .NET Standard o .NET Core.

## <a name="migrate-aspnet-mvc-projects"></a>Migración de proyectos de ASP.NET MVC

El `System.Web` espacio de nombres y los tipos no existen en .net Core. Cuando se analizan las dependencias y se usan herramientas como `try-convert` , no se ofrecen muchas sugerencias para la migración automática de proyectos de ASP.NET MVC y el código que hace referencia a ellos `System.Web` . Para estos proyectos, deberá empezar con un nuevo proyecto Web ASP.NET Core y migrar manualmente los archivos a este proyecto.

En general, se recomienda minimizar la cantidad de lógica de negocios de una aplicación en su nivel de interfaz de usuario. También es mejor mantener los controladores y las vistas pequeños. Las aplicaciones que han seguido esta guía serán más fáciles de portar que las que tienen una cantidad significativa de lógica en el proyecto Web ASP.NET. Si tiene una aplicación que está pensando en trasladar, pero aún no ha iniciado el proceso, tenga esto en cuenta a medida que la mantiene. Cualquier esfuerzo que se ponga en reducir la cantidad de código que se encuentra en el proyecto de ASP.NET MVC o Web API probablemente dará lugar a menos trabajo cuando llegue el momento de migrar la aplicación.

En el siguiente capítulo se profundiza en los detalles sobre cómo migrar de proyectos de ASP.NET MVC y Web API a proyectos de ASP.NET Core. En el capítulo anterior se han explicado las principales diferencias entre las aplicaciones. Una vez que la estructura básica del proyecto está en su lugar, la migración de controladores y vistas individuales suele ser sencilla, especialmente si se centra principalmente en las responsabilidades Web.

## <a name="references"></a>Referencias

- [Herramienta del Asistente para actualización de .NET](https://aka.ms/dotnet-upgrade-assistant)
- [herramienta try-Convert](https://github.com/dotnet/try-convert)
- [herramienta apiport](https://github.com/microsoft/dotnet-apiport)

>[!div class="step-by-step"]
>[Anterior](identify-migration-sequence.md)
>[Siguiente](strategies-migrating-in-production.md)
