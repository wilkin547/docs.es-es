---
title: Introducción a .NET Core con Visual Studio para Mac
description: Este tema le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.
ms.date: 12/19/2019
ms.openlocfilehash: 4cd7e311411bce62698e291e763227496877ea39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75740495"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Introducción a .NET Core en macOS con Visual Studio para Mac

Visual Studio para Mac proporciona un entorno de desarrollo integrado (IDE) completo para el desarrollo de aplicaciones .NET Core. Este artículo le guía en la creación de una aplicación de consola sencilla con Visual Studio para Mac y .NET Core.

> [!NOTE]
> Sus comentarios son muy importantes. Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:
>
> * En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores. Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/spaces/8/index.html).
> * Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Requisitos previos

Consulte el artículo [Dependencias y requisitos de .NET Core](../install/dependencies.md?pivots=os-macos).

Consulte el artículo [Compatibilidad de .NET Core](/visualstudio/mac/net-core-support) para asegurarse de que usa una versión compatible de .NET Core.

## <a name="get-started"></a>Primeros pasos

Si ya ha instalado los requisitos previos y Visual Studio para Mac, omita esta sección y proceda con [Creación de un proyecto](#creating-a-project). Siga estos pasos para instalar los requisitos previos y Visual Studio para Mac:

Descargue el [instalador de Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Ejecute el instalador. Lea y acepte el contrato de licencia. Durante la instalación, seleccione la opción de instalar .NET Core. Se le proporciona la oportunidad de instalar Xamarin, una tecnología de desarrollo de aplicaciones móviles multiplataforma. La instalación de Xamarin y sus componentes relacionados es opcional para el desarrollo de .NET Core. Para ver un tutorial del proceso de instalación de Visual Studio para Mac, consulte la [documentación de Visual Studio para Mac](/visualstudio/mac/). Una vez completada la instalación, inicie el IDE de Visual Studio para Mac.

## <a name="creating-a-project"></a>Creación de un proyecto

1. Seleccione **Nuevo** en la ventana de inicio.

   ![Botón Nuevo en la pantalla Inicio de Visual Studio para Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación** en el nodo **.NET Core**. Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.

   ![Lista de plantillas de Nuevo proyecto](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. Si tiene instalada más de una versión de .NET Core, seleccione el marco de destino del proyecto.

1. Escriba "HelloWorld" en **Nombre de proyecto**. Seleccione **Crear**.

   ![Configuración del cuadro de diálogo de nueva aplicación de consola](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. Espere mientras se restauran las dependencias del proyecto. El proyecto tiene un único archivo de C#, *Program.cs*, que contiene una clase `Program` con un método `Main`. La instrucción `Console.WriteLine` genera la salida "¡Hola a todos!" en la consola cuando se ejecuta la aplicación.

   ![Ventana principal con el archivo Program.cs abierto](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a>Ejecutar la aplicación

Ejecute la aplicación en modo de depuración con ⌘ ↵ (comando + ENTRAR) o en modo de versión ⌥ ⌘ ↵ (opción + comando + ENTRAR).

![El panel de salida de la aplicación muestra ¡Hola a todos!](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a>Paso siguiente

El tema [Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac](using-on-mac-vs-full-solution.md) le muestra cómo crear una solución completa de .NET Core que incluye una biblioteca reutilizable y pruebas unitarias.
