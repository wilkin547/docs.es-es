---
title: Símbolo del sistema para desarrolladores de Visual Studio
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: f028281d477284acf3ac4dac63f5ddbbd79f5259
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715842"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Símbolo del sistema para desarrolladores de Visual Studio

El Símbolo del sistema para desarrolladores de Visual Studio permite usar herramientas de .NET Framework más fácilmente. Es un símbolo del sistema que establece automáticamente variables de entorno específicas. Una vez abierto el Símbolo del sistema para desarrolladores, puede escribir los comandos para [herramientas de .NET Framework](index.md) como `ildasm` o `clrver`.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a>Búsqueda del símbolo del sistema en el equipo

Es posible que tenga varios símbolos del sistema, en función de la versión de Visual Studio y de los SDK y las cargas de trabajo adicionales que haya instalado. Si los pasos siguientes no funcionan, puede intentar [buscar manualmente los archivos en el equipo](#manually-locate-the-files-on-your-machine) o [ejecutar el símbolo del sistema desde Visual Studio](#start-the-command-prompt-from-inside-visual-studio).

### <a name="windows-10"></a>Windows 10

1. Seleccione **Inicio** ![Tecla del logotipo de Windows del teclado.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) y desplácese hasta la letra **V**.

1. Expanda la carpeta **Visual Studio 2019**.

1. Elija el **Símbolo del sistema para desarrolladores de VS 2019** (o el símbolo del sistema que quiera usar).

   Como alternativa, puede empezar a escribir el nombre del símbolo del sistema en el cuadro de búsqueda de la barra de tareas y elegir el resultado que desee a medida que la lista de resultados empiece a mostrar las coincidencias de búsqueda.

   ![GIF animado que muestra el comportamiento de búsqueda en Windows 10](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a>Windows 8.1

1. Vaya a la pantalla **Inicio** al presionar la tecla de logotipo de Windows ![Tecla de logotipo de Windows en el teclado.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) en el teclado, por ejemplo.

1. En la pantalla **Inicio**, presione **Ctrl**+**Tabulador** para abrir la lista **Aplicaciones** y presione **V**. Esto muestra una lista que incluye todos los símbolos del sistema de Visual Studio instalados.

1. Elija el **Símbolo del sistema para desarrolladores de VS 2019** (o el símbolo del sistema que quiera usar).

### <a name="windows-7"></a>Windows 7

1. Elija **Inicio** y, a continuación, expanda **Todos los programas**.

1. Elija **Visual Studio 2019** > **Herramientas de Visual Studio** > **Símbolo del sistema para desarrolladores de VS 2019**, o bien el símbolo del sistema que quiera usar.

   ![Menú Inicio de Windows 7 con el símbolo del sistema resaltado](./media/developer-command-prompt-for-vs/windows7-menu.png)

Si tiene instalados otros SDK, como el [SDK de Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versiones anteriores](https://developer.microsoft.com/windows/downloads/sdk-archive), es posible que vea símbolos del sistema adicionales. Consulte la documentación de cada herramienta para conocer la versión del símbolo del sistema que debe utilizar.

## <a name="manually-locate-the-files-on-your-machine"></a>Buscar manualmente los archivos en el equipo

Normalmente, los accesos directos de los símbolos del sistema que haya instalado se colocan en la carpeta **Menú Inicio** para Visual Studio; por ejemplo, en *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*. Pero si por alguna razón, la búsqueda del símbolo del sistema no produce los resultados esperados, puede intentar buscar manualmente el acceso directo en el equipo. Pruebe a buscar el nombre del archivo de símbolo del sistema; por ejemplo, *VsDevCmd.bat* o vaya a la carpeta de herramientas; por ejemplo, *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (la ruta de acceso cambia según la versión de Visual Studio, la edición y la ubicación de instalación).

## <a name="start-the-command-prompt-from-inside-visual-studio"></a>Iniciar el símbolo del sistema desde Visual Studio

Para un acceso más sencillo, puede agregar el Símbolo del sistema para desarrolladores o cualquier otro símbolo del sistema al menú Herramientas de Visual Studio. Para que la herramienta esté disponible, agréguela a la lista de herramientas externas. Estos son los pasos:

1. Abra Visual Studio.

1. En la ventana de inicio, elija **Continuar sin código**.

1. En la barra de menús, elija **Herramientas** > **Herramientas externas**.

1. En el cuadro de diálogo **Herramientas externas**, elija el botón **Agregar**. Aparecerá una nueva entrada.

1. Escriba el **Título** correspondiente al nuevo elemento de menú (por ejemplo, `Command Prompt`).

1. En el campo **Comando**, especifique el archivo que quiere iniciar, como `%comspec%` o `C:\Windows\System32\cmd.exe`.

1. En el campo **Argumentos** indique dónde se encuentra el símbolo del sistema específico que quiere usar como, por ejemplo, `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`. Este comando inicia el Símbolo del sistema para desarrolladores instalado con Visual Studio 2019 Community. Cambie este valor según la ubicación de instalación, la edición y la versión de Visual Studio.

1. En el campo **Directorio inicial**, especifique el directorio en el que se iniciará el símbolo del sistema. Elija un valor como **Directorio del proyecto** seleccionando la flecha situada junto al campo.

1. Elija el botón **Aceptar** .

   ![Cuadro de diálogo Herramientas externas con los valores de campo rellenados.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   Se agregará el nuevo elemento de menú y podrá acceder al símbolo del sistema desde el menú Herramientas.

   ![Elemento de menú del símbolo del sistema en Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a>Vea también

- [Herramientas de .NET Framework](index.md)
- [Administrar herramientas externas](/visualstudio/ide/managing-external-tools)
- [Uso del conjunto de herramientas de Microsoft C++ desde la línea de comandos](/cpp/build/building-on-the-command-line)
