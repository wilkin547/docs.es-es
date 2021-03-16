---
title: Desarrollo multiplataforma con la Biblioteca de clases portable
description: Cree aplicaciones y bibliotecas multiplataforma para plataformas de Microsoft de forma rápida y sencilla mediante el tipo de proyecto de biblioteca de clases portable en .NET.
ms.date: 09/17/2018
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: ced595f62249609f4524d0b4b7bf734929619bfd
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "102402255"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Desarrollo multiplataforma con la biblioteca de clases portable

El tipo de proyecto de biblioteca de clases portable de Visual Studio sirve para crear aplicaciones multiplataforma y bibliotecas para plataformas de Microsoft de forma rápida y sencilla.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Las bibliotecas de clases portables reducen el tiempo y el coste empleados en desarrollar y probar código. Use este tipo de proyecto para escribir y compilar ensamblados de .NET Framework portables; a continuación, haga referencia a esos ensamblados desde aplicaciones diseñadas para varias plataformas como, por ejemplo, .NET Framework, iOS o Mac.

Puede cambiar de plataforma incluso después de haber creado un proyecto de Biblioteca de clases portable en Visual Studio y de haber empezado a desarrollarlo. Visual Studio compila la biblioteca con los ensamblados nuevos, con lo que podrá identificar los cambios que necesita hacer en el código.

## <a name="create-a-portable-class-library-project"></a>Creación de un proyecto de biblioteca de clases portable

Para crear una biblioteca de clases portable, use la plantilla que se proporciona en Visual Studio. Cree un nuevo proyecto (**Archivo** > **Nuevo proyecto**) y, en el cuadro de diálogo **Nuevo proyecto**, seleccione el lenguaje de programación (Visual C# o Visual Basic). A continuación, seleccione la plantilla **Biblioteca de clases (portable heredada)** . Escriba el nombre del proyecto y seleccione **Aceptar**.

Aparecerá el cuadro de diálogo **Agregar biblioteca de clases portable**. Elija dos o más destinos y, después, elija **Aceptar**.

![Adición de destinos de biblioteca de clases portable en Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Modificación de los destinos

Puede cambiar las plataformas de destino de un proyecto de biblioteca de clases portable cuando se crea o cuando se inicia el desarrollo. Si desea cambiar los destinos después de haber creado el proyecto, vaya al **Explorador de soluciones**, abra el menú contextual del proyecto de biblioteca de clases portable (no la solución) y elija **Propiedades**. En la página de propiedades del proyecto, la pestaña **Biblioteca** muestra las plataformas a las que actualmente va dirigido el proyecto.

![Propiedades del proyecto para la biblioteca de clases portable en Visual Studio](media/pcl-project-properties.png)

Para agregar o quitar destinos, elija el botón **Cambiar** y, a continuación, active y desactive las casillas correspondientes.

Al modificar los destinos, las API que tiene a su disposición para desarrollar el proyecto cambiarán para corresponderse con las opciones seleccionadas. Visual Studio notifica los errores y las advertencias que pueden producirse como resultado del cambio de destinos.

Si desea evaluar la portabilidad de los ensamblados antes de realizar cambios en Visual Studio, puede usar el [Analizador de portabilidad de .NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).

## <a name="supported-types-and-members"></a>Tipos y miembros compatibles

Los tipos y miembros disponibles en los proyectos de Biblioteca de clases portable están limitados por varios factores de compatibilidad:

- Deben compartirse en los destinos seleccionados.

- Deben comportarse de manera similar en todos esos destinos.

- No deben ser candidatos para desuso.

- Deben tener sentido en un entorno portable, especialmente cuando los miembros auxiliares no son portátiles.

Si un miembro es compatible con la Biblioteca de clases portable y con los destinos seleccionados, aparecerá en su proyecto en IntelliSense. No obstante, recuerde que una API puede ser compatible con la Biblioteca de clases portable, pero si esa API se puede usar dependerá de los destinos que se seleccionen.

## <a name="api-differences-in-the-portable-class-library"></a>Diferencias de API en la Biblioteca de clases portable

Para que los ensamblados de la Biblioteca de clases portable sean compatibles en todas las plataformas admitidas, algunos miembros se han modificado ligeramente en la Biblioteca de clases portable.

## <a name="use-the-portable-class-library"></a>Uso de la biblioteca de clases portable

Después de compilar el proyecto de Biblioteca de clases portable, haga referencia a él desde otros proyectos. Puede hacer referencia al proyecto o a ensamblados específicos que contengan las clases a las que desea obtener acceso.

Para ejecutar una aplicación que haga referencia a un ensamblado de Biblioteca de clases portable, debe estar instalada en el equipo la versión requerida (o una versión posterior) de las plataformas de destino. Visual Studio contiene todos los marcos necesarios para poder ejecutar la aplicación sin modificaciones adicionales en el equipo que utilizó para desarrollar la aplicación.

### <a name="deploy-a-universal-windows-app"></a>Implementación de una aplicación universal de Windows

Cuando cree una aplicación universal de Windows que haga referencia a un ensamblado de biblioteca de clases portable, no necesitará realizar pasos adicionales, ya que el paquete de la aplicación incluye todo lo necesario para implementar la aplicación.

### <a name="deploy-a-net-framework-app"></a>Implementación de una aplicación de .NET Framework

Cuando implemente una aplicación de .NET Framework que haga referencia a un ensamblado de Biblioteca de clases portable, especifique una dependencia en la versión correcta de .NET Framework. Al especificar esta dependencia, se asegura de que la versión requerida se instala con la aplicación.

- Para crear una dependencia con la implementación ClickOnce: en el **Explorador de soluciones**, elija el nodo del proyecto que desea publicar. (Este es el proyecto que hace referencia al proyecto de biblioteca de clases portable). En la barra de menús, seleccione **Proyecto** > **Propiedades** y, a continuación, elija la pestaña **Publicar**. En la página **Publicar**, elija **Requisitos previos**. Seleccione la versión de .NET Framework necesaria como requisito previo.

- Para crear una dependencia con un proyecto de instalación: en el **Explorador de soluciones**, elija el proyecto de instalación. En la barra de menús, seleccione **Proyecto** > **Propiedades** > **Requisitos previos**. Seleccione la versión de .NET Framework necesaria como requisito previo.

Para obtener más información sobre cómo implementar aplicaciones de .NET Framework, consulte [Guía de implementación para desarrolladores](../../framework/deployment/deployment-guide-for-developers.md).

## <a name="see-also"></a>Vea también

- [Using Portable Class Library with MVVM](using-portable-class-library-with-model-view-view-model.md) (Uso de bibliotecas de clases portables con MVVM)
- [App Resources for Libraries That Target Multiple Platforms](app-resources-for-libraries-that-target-multiple-platforms.md) (Recursos de aplicación para bibliotecas destinadas a varias plataformas)
- [Analizador de portabilidad de .NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](support-for-windows-store-apps-and-windows-runtime.md)
- [Implementación](../../framework/deployment/net-framework-applications.md)
