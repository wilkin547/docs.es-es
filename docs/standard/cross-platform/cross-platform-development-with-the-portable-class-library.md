---
title: Desarrollo multiplataforma con la Biblioteca de clases portable
description: Cree aplicaciones y bibliotecas multiplataforma para plataformas de Microsoft de forma rápida y sencilla mediante el tipo de proyecto de biblioteca de clases portable en .NET.
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: be1a49f7da7ce98f9e5e3ff8d927ce5230bfa8d8
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769150"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Desarrollo multiplataforma con la biblioteca de clases portable

El tipo de proyecto de biblioteca de clases portable en Visual Studio le ayuda a compilar aplicaciones y bibliotecas multiplataforma para plataformas de Microsoft de forma rápida y sencilla.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Las bibliotecas de clases portables reducen el tiempo y el coste empleados en desarrollar y probar código. Use este tipo de proyecto para escribir y compilar ensamblados de .NET Framework portátiles y luego hacer referencia a esos ensamblados desde aplicaciones destinadas a varias plataformas, como .NET Framework, iOS o Mac.

Puede cambiar de plataforma incluso después de haber creado un proyecto de Biblioteca de clases portable en Visual Studio y de haber empezado a desarrollarlo. Visual Studio compila la biblioteca con los nuevos ensamblados, lo que le ayuda a identificar los cambios que debe realizar en el código.

## <a name="create-a-portable-class-library-project"></a>Crear un proyecto de biblioteca de clases portable

Para crear una biblioteca de clases portable, use la plantilla que se proporciona en Visual Studio. Cree un nuevo proyecto (**archivo**  >  **nuevo proyecto**) y, en el cuadro de diálogo **nuevo proyecto** , seleccione el lenguaje de programación (Visual C# o Visual Basic). A continuación, seleccione la plantilla **biblioteca de clases (Legacy portable)** . Escriba un nombre para el proyecto y elija **Aceptar**.

Aparece el cuadro de diálogo **Agregar biblioteca de clases portable** . Elija dos o más destinos y, después, elija **Aceptar**.

![Agregar destinos de biblioteca de clases portable en Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Cambiar destinos

Puede cambiar las plataformas de destino de un proyecto de biblioteca de clases portable cuando se crea o cuando se inicia el desarrollo. Si desea cambiar los destinos una vez creado el proyecto, en **Explorador de soluciones**, abra el menú contextual del proyecto de biblioteca de clases portable (no de la solución) y, a continuación, elija **propiedades**. En la página de propiedades del proyecto, la pestaña **biblioteca** muestra las plataformas a las que el proyecto está destinado actualmente.

![Propiedades del proyecto para la biblioteca de clases portable en Visual Studio](media/pcl-project-properties.png)

Para agregar o quitar destinos, elija el botón **cambiar** y, a continuación, Active y desactive las casillas correspondientes.

Al modificar los destinos, las API que tiene a su disposición para desarrollar el proyecto cambiarán para corresponderse con las opciones seleccionadas. Visual Studio notifica los errores y las advertencias que pueden producirse como resultado del cambio de destinos.

Si desea evaluar la portabilidad de los ensamblados antes de realizar cambios en Visual Studio, puede usar el analizador de [portabilidad de .net](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).

## <a name="supported-types-and-members"></a>Tipos y miembros compatibles

Los tipos y miembros disponibles en los proyectos de Biblioteca de clases portable están limitados por varios factores de compatibilidad:

- Deben compartirse en los destinos seleccionados.

- Deben comportarse de manera similar en todos esos destinos.

- No deben ser candidatos para desuso.

- Deben tener sentido en un entorno portable, especialmente cuando los miembros auxiliares no son portátiles.

Si un miembro es compatible con la Biblioteca de clases portable y con los destinos seleccionados, aparecerá en su proyecto en IntelliSense. No obstante, recuerde que una API puede ser compatible con la Biblioteca de clases portable, pero si esa API se puede usar dependerá de los destinos que se seleccionen.

## <a name="api-differences-in-the-portable-class-library"></a>Diferencias de API en la Biblioteca de clases portable

Para que los ensamblados de la Biblioteca de clases portable sean compatibles en todas las plataformas admitidas, algunos miembros se han modificado ligeramente en la Biblioteca de clases portable.

## <a name="use-the-portable-class-library"></a>Usar la biblioteca de clases portable

Después de compilar el proyecto de Biblioteca de clases portable, haga referencia a él desde otros proyectos. Puede hacer referencia al proyecto o a ensamblados específicos que contengan las clases a las que desea obtener acceso.

Para ejecutar una aplicación que haga referencia a un ensamblado de Biblioteca de clases portable, debe estar instalada en el equipo la versión requerida (o una versión posterior) de las plataformas de destino. Visual Studio contiene todos los marcos necesarios para poder ejecutar la aplicación sin modificaciones adicionales en el equipo que utilizó para desarrollar la aplicación.

### <a name="deploy-a-universal-windows-app"></a>Implementar una aplicación universal de Windows

Al crear una aplicación universal de Windows que hace referencia a un ensamblado de biblioteca de clases portable, todo lo que necesita para implementar la aplicación se incluye en el paquete de la aplicación y no es necesario realizar más pasos.

### <a name="deploy-a-net-framework-app"></a>Implementación de una aplicación .NET Framework

Cuando implemente una aplicación de .NET Framework que haga referencia a un ensamblado de Biblioteca de clases portable, especifique una dependencia en la versión correcta de .NET Framework. Al especificar esta dependencia, se asegura de que la versión requerida se instala con la aplicación.

- Para crear una dependencia con la implementación ClickOnce: en **Explorador de soluciones**, elija el nodo del proyecto que desea publicar. (Este es el proyecto que hace referencia al proyecto de biblioteca de clases portable). En la barra de menús, **Project**elija  >  **propiedades**del proyecto y, a continuación, elija la pestaña **publicar** . En la página **publicar** , elija **requisitos previos**. Seleccione la versión de .NET Framework necesaria como requisito previo.

- Para crear una dependencia con un proyecto de instalación: en **Explorador de soluciones**, elija el proyecto de instalación. En la barra de menús, **Project**elija  >  **Properties**  >  **requisitos previos**de las propiedades del proyecto. Seleccione la versión de .NET Framework necesaria como requisito previo.

Para obtener más información sobre la implementación de .NET Framework aplicaciones, consulte la [Guía de implementación para desarrolladores](../../framework/deployment/deployment-guide-for-developers.md).

## <a name="see-also"></a>Consulte también

- [Uso de la biblioteca de clases portable con MVVM](using-portable-class-library-with-model-view-view-model.md)
- [Recursos de la aplicación para bibliotecas destinadas a varias plataformas](app-resources-for-libraries-that-target-multiple-platforms.md)
- [Analizador de portabilidad de .NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución](support-for-windows-store-apps-and-windows-runtime.md)
- [Implementación](../../framework/deployment/net-framework-applications.md)
