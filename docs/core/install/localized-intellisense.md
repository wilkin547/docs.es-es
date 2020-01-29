---
title: Instalación de archivos de IntelliSense localizados
description: Obtenga información sobre cómo configurar su máquina de desarrollo con el fin de usar archivos de IntelliSense localizados para los proyectos de .NET Core en Visual Studio.
ms.date: 01/23/2020
ms.openlocfilehash: 58b462507edf953a6c28aadbb9e3239a5cbe05b2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733651"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a>Procedimiento para instalar archivos de IntelliSense localizados para .NET Core

[IntelliSense](/visualstudio/ide/using-intellisense) es una característica que ayuda a completar código y que está disponible en diferentes entornos de desarrollo integrado (IDE), como Visual Studio. De manera predeterminada, al desarrollar proyectos de .NET Core, el SDK solo incluye la versión en inglés de los archivos de IntelliSense. En este artículo, se explica lo siguiente:

- Procedimiento para instalar la versión localizada de estos archivos.
- Procedimiento para modificar la instalación de Visual Studio para usar otro idioma.

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core) o una versión posterior.
- [Versión 16.3 de Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) u otra posterior.

## <a name="download-and-install-the-localized-intellisense-files"></a>Descarga e instalación de los archivos de IntelliSense localizados

> [!IMPORTANT]
> Para poder realizar este procedimiento, necesita tener permiso de administrador para copiar los archivos de IntelliSense en la carpeta de instalación de .NET Core.

1. Vaya a la página [Descarga de archivos de IntelliSense](https://dotnet.microsoft.com/download/dotnet-core/intellisense).

1. Descargue el archivo de IntelliSense en el idioma y la versión que prefiera.

1. Extraiga el contenido del archivo ZIP.

1. Vaya a la carpeta Intellisense de .NET Core.

   1. Vaya a la carpeta de instalación de .NET Core. De manera predeterminada, se encuentra en *%Archivos de programa%\dotnet\packs*.
   1. Elija para qué SDK quiere instalar el archivo de IntelliSense y vaya a la ruta de acceso correspondiente. Dispone de las siguientes opciones:

      | Tipo de SDK        | Ruta de acceso                               |
      | --------------- | ---------------------------------- |
      | .NET Core       | *Microsoft.NETCore.App.Ref*        |
      | Escritorio de Windows | *Microsoft.WindowsDesktop.App.Ref* |
      | .NET Standard   | *NETStandard.Library.Ref*          |
   
   1. Vaya a la versión para la que quiera instalar el archivo de IntelliSense localizado. Por ejemplo, la *3.1.0*.
   1. Abra la carpeta *ref*.
   1. Abra la carpeta del moniker. Por ejemplo, *netcoreapp3.1*.

   Así pues, la ruta de acceso completa tendrá un aspecto similar al siguiente: *C:\Archivos de programa\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.

1. Cree una subcarpeta en la carpeta del moniker que acaba de abrir. El nombre de la carpeta indicará el idioma que quiere usar. En la siguiente tabla, se especifican las diferentes opciones:

   | Lenguaje              | Nombre de carpeta |
   | --------------------- | ----------- |
   | Portugués (Brasil)  | *pt-br*     |
   | Chino simplificado  | *zh-hans*   |
   | Chino tradicional | *zh-hant*   |
   | Francés                | *fr*        |
   | Alemán                | *de*        |
   | Italiano               | *it*        |
   | Japonés              | *ja*        |
   | Coreano                | *ko*        |
   | Ruso               | *ru*        |
   | Español               | *es*        |

1. Copie en esta nueva carpeta los archivos *.xml* que ha extraído en el paso 3. Los archivos *.xml* se mostrarán agrupados según las diferentes carpetas de SDK, de modo que debe copiarlos en la del SDK que haya elegido en el paso 4.

## <a name="modify-visual-studio-language"></a>Modificación del idioma de Visual Studio

Para que Visual Studio use otro idioma para IntelliSense, instale el paquete de idioma correspondiente. Esto se puede realizar [durante la instalación](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) o después modificando la instalación de Visual Studio. Si ya tiene Visual Studio configurado en el idioma que quiere, su instalación de IntelliSense está lista.

### <a name="install-the-language-pack"></a>Instalación del paquete de idioma

Si no ha instalado el paquete de idioma deseado durante la configuración, actualice Visual Studio como se indica a continuación para instalar el paquete de idioma:

> [!IMPORTANT]
> Para instalar, actualizar o modificar Visual Studio, debe iniciar sesión con una cuenta que tenga permisos de administrador. Para obtener más información, consulte [Permisos de usuario y Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).

1. Busque el instalador de Visual Studio en su equipo.

   Por ejemplo, en un equipo que ejecuta Windows 10, seleccione **Iniciar** y, después, desplácese hasta la letra **I** donde lo verá como **Instalador de Visual Studio**.

   ![Apertura del Instalador de Visual Studio desde Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > También pude encontrar el instalador de Visual Studio en la siguiente ubicación:
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   Es posible que tenga que actualizar el instalador antes de continuar. De ser así, siga las indicaciones.

1. En el instalador, busque la edición de Visual Studio a la que quiera agregar el paquete de idioma y, luego, elija **Modificar**.

   ![Actualización o modificación de Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > Si no ve el botón **Modificar**, pero sí el botón **Actualizar**, significa que necesita actualizar su versión de Visual Studio para poder modificar su instalación.
   > Cuando haya finalizado la actualización, aparecerá el botón **Modificar**.

1. En la pestaña **Paquetes de idioma**, seleccione o anule la selección de los idiomas que quiera instalar o desinstalar.

   ![Pestaña Paquetes de idioma de Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. Elija **Modificar**. Se inicia la actualización.

### <a name="modify-language-settings-in-visual-studio"></a>Modificación de la configuración de idioma en Visual Studio

Una vez que haya instalado los paquete de idioma deseados, modifique la configuración de Visual Studio para usar otro idioma:

1. Abra Visual Studio.

1. En la ventana de inicio, elija **Continuar sin código**.

1. En la barra de menús, seleccione **Herramientas** > **Opciones**. Se abrirá el cuadro de diálogo Opciones.

1. En el nodo **Entorno**, seleccione **Configuración internacional**.

1. En la lista desplegable **Idioma**, seleccione el que quiera usar. Elija **Aceptar**. 

1. Aparecerá un cuadro de diálogo en el que se le informará de que debe reiniciar Visual Studio para que se apliquen los cambios. Elija **Aceptar**.

1. Reinicie Visual Studio.

Después de esto, IntelliSense deberá funcionar según lo esperado al abrir un proyecto de .NET Core que tenga como destino la versión de los archivos de IntelliSense que acaba de instalar.

## <a name="see-also"></a>Vea también

- [IntelliSense en Visual Studio](/visualstudio/ide/using-intellisense)
