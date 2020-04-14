---
title: Desarrollo multiplataforma con la Biblioteca de clases portable
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: 7caddd7361b8f364762fb4357e35cb918ae99263
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242808"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Desarrollo multiplataforma con la Biblioteca de Clases Portable

El tipo de proyecto Biblioteca de clases portable en Visual Studio le ayuda a crear aplicaciones y bibliotecas multiplataforma para plataformas Microsoft de forma rápida y sencilla.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Las bibliotecas de clases portables reducen el tiempo y el coste empleados en desarrollar y probar código. Use este tipo de proyecto para escribir y compilar ensamblados portátiles de .NET Framework y, a continuación, haga referencia a los ensamblados de aplicaciones destinadas a varias plataformas como .NET Framework, iOS o Mac.

Puede cambiar de plataforma incluso después de haber creado un proyecto de Biblioteca de clases portable en Visual Studio y de haber empezado a desarrollarlo. Visual Studio compila la biblioteca con los nuevos ensamblados, lo que le ayuda a identificar los cambios que necesita realizar en el código.

## <a name="create-a-portable-class-library-project"></a>Crear un proyecto de biblioteca de clases portátil

Para crear una biblioteca de clases portable, use la plantilla proporcionada en Visual Studio. Cree un nuevo proyecto **(Archivo** > **nuevo proyecto**) y, en el cuadro de diálogo Nuevo **proyecto,** seleccione el lenguaje de programación (Visual C o Visual Basic). A continuación, seleccione la plantilla Biblioteca de **clases (Portable heredado).** Escriba un nombre para el proyecto y elija **Aceptar**.

Aparece el cuadro de diálogo Agregar biblioteca de **clases portátil.** Elija dos o más destinos y, a continuación, elija **OK**.

![Agregar destinos de biblioteca de clases portátiles en Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Cambiar objetivos

Puede cambiar las plataformas de destino de un proyecto de biblioteca de clases portátil al crearlo o después de iniciar el desarrollo. Si desea cambiar los destinos después de crear el proyecto, en el **Explorador**de soluciones , abra el menú contextual del proyecto Biblioteca de clases portable (no la solución) y, a continuación, elija **Propiedades**. En la página de propiedades del proyecto, la pestaña **Biblioteca** muestra las plataformas a las que se dirige actualmente el proyecto.

![Propiedades del proyecto para la biblioteca de clases portable en Visual Studio](media/pcl-project-properties.png)

Para agregar o quitar destinos, elija el botón **Cambiar** y, a continuación, active y desactive las casillas de verificación adecuadas.

Al modificar los destinos, las API que tiene a su disposición para desarrollar el proyecto cambiarán para corresponderse con las opciones seleccionadas. Visual Studio notifica los errores y las advertencias que pueden producirse como resultado del cambio de destinos.

Si desea evaluar la portabilidad de los ensamblados antes de realizar cambios en Visual Studio, puede usar el Analizador de portabilidad de [.NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer).

## <a name="supported-types-and-members"></a>Tipos y miembros compatibles

Los tipos y miembros disponibles en los proyectos de Biblioteca de clases portable están limitados por varios factores de compatibilidad:

- Deben compartirse en los destinos seleccionados.

- Deben comportarse de manera similar en todos esos destinos.

- No deben ser candidatos para desuso.

- Deben tener sentido en un entorno portable, especialmente cuando los miembros auxiliares no son portátiles.

Si un miembro es compatible con la Biblioteca de clases portable y con los destinos seleccionados, aparecerá en su proyecto en IntelliSense. No obstante, recuerde que una API puede ser compatible con la Biblioteca de clases portable, pero si esa API se puede usar dependerá de los destinos que se seleccionen.

## <a name="api-differences-in-the-portable-class-library"></a>Diferencias de API en la Biblioteca de clases portable

Para que los ensamblados de la Biblioteca de clases portable sean compatibles en todas las plataformas admitidas, algunos miembros se han modificado ligeramente en la Biblioteca de clases portable.

## <a name="use-the-portable-class-library"></a>Utilice la biblioteca de clases portátil

Después de compilar el proyecto de Biblioteca de clases portable, haga referencia a él desde otros proyectos. Puede hacer referencia al proyecto o a ensamblados específicos que contengan las clases a las que desea obtener acceso.

Para ejecutar una aplicación que haga referencia a un ensamblado de Biblioteca de clases portable, debe estar instalada en el equipo la versión requerida (o una versión posterior) de las plataformas de destino. Visual Studio contiene todos los marcos necesarios para poder ejecutar la aplicación sin modificaciones adicionales en el equipo que utilizó para desarrollar la aplicación.

### <a name="deploy-a-universal-windows-app"></a>Implementar una aplicación universal de Windows

Al crear una aplicación universal de Windows que hace referencia a un ensamblado de biblioteca de clases portable, todo lo que necesita para implementar la aplicación se incluye en el paquete de la aplicación y no se requieren pasos adicionales.

### <a name="deploy-a-net-framework-app"></a>Implementar una aplicación de .NET Framework

Cuando implemente una aplicación de .NET Framework que haga referencia a un ensamblado de Biblioteca de clases portable, especifique una dependencia en la versión correcta de .NET Framework. Al especificar esta dependencia, se asegura de que la versión requerida se instala con la aplicación.

- Para crear una dependencia con ClickOnce Implementación: en el **Explorador**de soluciones , elija el nodo de proyecto para el proyecto que desea publicar. (Este es el proyecto que hace referencia al proyecto de biblioteca de clases portable.) En la barra de menús, elija**Propiedades**del **proyecto** > y, a continuación, elija la pestaña **Publicar.** En la página **Publish,** elija **Prerequisites**. Seleccione la versión de .NET Framework necesaria como requisito previo.

- Para crear una dependencia con un proyecto de instalación: en el Explorador de **soluciones**, elija el proyecto de instalación. En la barra de**menús,** elija **Requisitos** > previos de**propiedades** > del proyecto . Seleccione la versión de .NET Framework necesaria como requisito previo.

Para obtener más información acerca de la implementación de aplicaciones de .NET Framework, vea Guía de [implementación para desarrolladores](../../../docs/framework/deployment/deployment-guide-for-developers.md).

## <a name="see-also"></a>Consulte también

- [Uso de la biblioteca de clases portable con MVVM](using-portable-class-library-with-model-view-view-model.md)
- [Recursos de aplicaciones para bibliotecas destinadas a varias plataformas](app-resources-for-libraries-that-target-multiple-platforms.md)
- [Analizador de portabilidad de .NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [Implementación](../../../docs/framework/deployment/net-framework-applications.md)
