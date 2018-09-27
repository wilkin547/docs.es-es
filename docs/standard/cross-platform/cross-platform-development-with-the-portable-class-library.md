---
title: Desarrollo multiplataforma con la Biblioteca de clases portable
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afaa8e118bb21e5c1e4f1c53b1d0d29ca6bb3bf5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47237272"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Desarrollo multiplataforma con la biblioteca de clases Portable

El tipo de proyecto de biblioteca de clases Portable en Visual Studio le ayuda a crear aplicaciones multiplataforma y bibliotecas para las plataformas de Microsoft de forma rápida y fácilmente.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Las bibliotecas de clases portables reducen el tiempo y el coste empleados en desarrollar y probar código. Use este tipo de proyecto para escribir y compilar ensamblados portables de .NET Framework y, a continuación, hacer referencia a esos ensamblados desde aplicaciones que tienen como destino varias plataformas como .NET Framework, iOS o Mac.

Puede cambiar de plataforma incluso después de haber creado un proyecto de Biblioteca de clases portable en Visual Studio y de haber empezado a desarrollarlo. Visual Studio compila la biblioteca con los nuevos ensamblados, lo que ayuda a identificar los cambios que debe realizar en el código.

## <a name="create-a-portable-class-library-project"></a>Crear un proyecto de biblioteca de clases Portable

Para crear una biblioteca de clases Portable, use la plantilla proporcionada en Visual Studio. Cree un nuevo proyecto (**archivo** > **nuevo proyecto**) y en el **nuevo proyecto** cuadro de diálogo, seleccione el lenguaje de programación (Visual C# o Visual Basic). A continuación, seleccione el **biblioteca de clases (portátil heredada)** plantilla. Escriba un nombre para el proyecto y elija **Aceptar**.

El **Agregar biblioteca de clases Portable** aparece el cuadro de diálogo. Elija dos o más destinos y, a continuación, elija **Aceptar**.

![Agregar destinos de biblioteca de clases portable en Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Cambiar los destinos

Puede cambiar las plataformas de destino de un proyecto de biblioteca de clases portable al crearlo o después de haber iniciado el desarrollo. Si desea cambiar los destinos después de crear el proyecto, en **el Explorador de soluciones**, abra el menú contextual para el proyecto de biblioteca de clases Portable (no la solución) y, a continuación, elija **propiedades** . En la página de propiedades del proyecto, el **biblioteca** pestaña muestra las plataformas que actualmente dirige el proyecto.

![Propiedades del proyecto de biblioteca de clases Portable en Visual Studio](media/pcl-project-properties.png)

Para agregar o quitar destinos, elija el **cambio** botón y, a continuación, active y desactive las casillas correspondientes.

Al modificar los destinos, las API que tiene a su disposición para desarrollar el proyecto cambiarán para corresponderse con las opciones seleccionadas. Visual Studio notifica los errores y las advertencias que pueden producirse como resultado del cambio de destinos.

Si desea evaluar la portabilidad de los ensamblados antes de realizar cambios en Visual Studio, puede usar el [.NET Portability Analyzer](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).

## <a name="supported-types-and-members"></a>Tipos y miembros compatibles

Los tipos y miembros disponibles en los proyectos de Biblioteca de clases portable están limitados por varios factores de compatibilidad:

-   Deben compartirse en los destinos seleccionados.

-   Deben comportarse de manera similar en todos esos destinos.

-   No deben ser candidatos para desuso.

-   Deben tener sentido en un entorno portable, especialmente cuando los miembros auxiliares no son portátiles.

Si un miembro es compatible con la Biblioteca de clases portable y con los destinos seleccionados, aparecerá en su proyecto en IntelliSense. No obstante, recuerde que una API puede ser compatible con la Biblioteca de clases portable, pero si esa API se puede usar dependerá de los destinos que se seleccionen.

## <a name="api-differences-in-the-portable-class-library"></a>Diferencias de API en la Biblioteca de clases portable

Para que los ensamblados de la Biblioteca de clases portable sean compatibles en todas las plataformas admitidas, algunos miembros se han modificado ligeramente en la Biblioteca de clases portable.

## <a name="use-the-portable-class-library"></a>Uso de la biblioteca de clases Portable

Después de compilar el proyecto de Biblioteca de clases portable, haga referencia a él desde otros proyectos. Puede hacer referencia al proyecto o a ensamblados específicos que contengan las clases a las que desea obtener acceso.

Para ejecutar una aplicación que haga referencia a un ensamblado de Biblioteca de clases portable, debe estar instalada en el equipo la versión requerida (o una versión posterior) de las plataformas de destino. Visual Studio contiene todos los marcos necesarios para poder ejecutar la aplicación sin modificaciones adicionales en el equipo que utilizó para desarrollar la aplicación.

### <a name="deploy-a-universal-windows-app"></a>Implementar una aplicación Windows Universal

Cuando se crea una aplicación Windows Universal que hace referencia a un ensamblado de biblioteca de clases Portable, todo lo que necesita para implementar la aplicación se incluye en el paquete de aplicación y se requiere ningún paso adicional.

### <a name="deploy-a-net-framework-app"></a>Implementar .NET Framework app

Cuando implemente una aplicación de .NET Framework que haga referencia a un ensamblado de Biblioteca de clases portable, especifique una dependencia en la versión correcta de .NET Framework. Al especificar esta dependencia, se asegura de que la versión requerida se instala con la aplicación.

-   Para crear una dependencia con implementación ClickOnce: en **el Explorador de soluciones**, elija el nodo del proyecto para el proyecto que desea publicar. (Este es el proyecto que hace referencia al proyecto de Biblioteca de clases portable). En la barra de menús, elija **proyecto** > **propiedades**y, a continuación, elija el **publicar** ficha. En el **publicar** página, elija **requisitos previos**. Seleccione la versión de .NET Framework necesaria como requisito previo.

-   Para crear una dependencia con un proyecto de instalación: en **el Explorador de soluciones**, elija el proyecto de instalación. En la barra de menús, elija **proyecto** > **propiedades** > **requisitos previos**. Seleccione la versión de .NET Framework necesaria como requisito previo.

Para obtener más información sobre cómo implementar aplicaciones de .NET Framework, vea [Deployment Guide for Developers](../../../docs/framework/deployment/deployment-guide-for-developers.md).

## <a name="see-also"></a>Vea también

- [Uso de la Biblioteca de clases portable con MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)
- [Recursos de aplicación para bibliotecas destinadas a varias plataformas](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)
- [Analizador de portabilidad de .NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [Implementación](../../../docs/framework/deployment/net-framework-applications.md)
