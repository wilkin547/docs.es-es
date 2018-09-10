---
title: Símbolo del sistema para desarrolladores de Visual Studio
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c95074190419dd3e984c7659ede917b83b97f08
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524721"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Símbolo del sistema para desarrolladores de Visual Studio

El símbolo del sistema para desarrolladores de Visual Studio establece automáticamente las variables de entorno que permiten usar fácilmente las herramientas de .NET Framework.

> [!div class="button"]
[Descarga de Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a>Búsqueda del símbolo del sistema en el equipo

Es posible que tenga varios símbolos del sistema, en función de la versión de Visual Studio y de los SDK adicionales que haya instalado. Por ejemplo, las versiones de 64 bits de Visual Studio proporcionan los símbolos del sistema de 32 y de 64 bits. (Las versiones de 32 y 64 bits de la mayoría de las herramientas son iguales; pero algunas herramientas realizan cambios específicos para los entornos de 32 o 64 bits). Si los pasos siguientes no funcionan, puede probar los que se describen en [Buscar manualmente los archivos en el equipo](#manually-locating-the-files-on-your-machine) o [Ejecutar el símbolo del sistema desde Visual Studio](#running-command-prompt-from-inside-visual-studio).

### <a name="in-windows-10"></a>En Windows 10

1. En el cuadro de búsqueda de la barra de tareas, comience a escribir el nombre de la herramienta, como `dev` o `developer command prompt`. Esto muestra una lista de las aplicaciones instaladas que coinciden con el patrón de búsqueda. Si busca un símbolo del sistema diferente, pruebe a escribir otro término de búsqueda, como `prompt`.

2. Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).

### <a name="in-windows-81"></a>En Windows 8.1

1. Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.

2. En la pantalla **Inicio**, presione `CTRL + TAB` para abrir la lista **Aplicaciones** y escriba `V`. Esto muestra una lista que incluye los símbolos del sistema de Visual Studio instalados.

3. Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).

### <a name="in-windows-8"></a>En Windows 8

1. Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.

2. En la pantalla **Inicio**, presione la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.

3. Elija el icono **Vista Aplicaciones** en la parte inferior de la pantalla y después escriba `V`. Esto muestra una lista que incluye los símbolos del sistema de Visual Studio instalados.

4. Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).

### <a name="in-windows-7"></a>En Windows 7

1. Elija **Inicio**, expanda **Todos los programas** y luego, **Microsoft Visual Studio**.

2. Según la versión de Visual Studio que tenga instalada, elija **Visual Studio Tools**, **Visual Studio Command Prompt** o el símbolo del sistema que quiera usar.

Si tiene instalados otros SDK, como el [SDK de Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versiones anteriores](https://developer.microsoft.com/windows/downloads/sdk-archive), es posible que vea símbolos del sistema adicionales para las arquitecturas ARM, x86 o x64. Consulte la documentación de cada herramienta para conocer la versión del símbolo del sistema que debe utilizar.

## <a name="manually-locate-the-files-on-your-machine"></a>Buscar manualmente los archivos en el equipo

Normalmente, los accesos directos de los símbolos del sistema que haya instalado se colocan en la carpeta **Menú Inicio** para Visual Studio; por ejemplo, en C:\ProgramData\Microsoft\Windows\Menú Inicio\Programas\Visual Studio 2017\Visual Studio Tools. Pero si por alguna razón, la búsqueda del símbolo del sistema no muestra los resultados esperados, puede intentar buscar manualmente el acceso directo en el equipo. Pruebe a buscar el nombre del archivo de símbolo del sistema; por ejemplo, *VsDevCmd.bat* o vaya a la carpeta de herramientas; por ejemplo, C:\Archivos de programa (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (la ruta de acceso cambia según la versión de Visual Studio, la edición y la ubicación de instalación).

## <a name="run-command-prompt-from-inside-visual-studio"></a>Ejecutar el símbolo del sistema desde Visual Studio

Para un acceso más sencillo, puede agregar el símbolo del sistema para desarrolladores de Visual Studio o cualquier otro símbolo del sistema al menú **Herramientas** de Visual Studio. Para que la herramienta esté disponible, agréguela a la lista de herramientas externas. Estos son los pasos:

1. Abra Visual Studio.

2. Seleccione el menú **Herramientas** y, después, elija **Herramientas externas**.

3. En el cuadro de diálogo **Herramientas externas**, elija el botón **Agregar**. Aparecerá una nueva entrada.

4. Escriba el **Título** correspondiente al nuevo elemento de menú (por ejemplo, `Command Prompt`).

5. En el campo **Comando**, especifique el archivo que quiere iniciar, como `%comspec%` o `C:\Windows\System32\cmd.exe`.

6. En el campo **Argumentos** indique dónde se encuentra el símbolo del sistema específico que quiere usar como, por ejemplo, `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (este comando inicia el símbolo del sistema para desarrolladores que se instala con Visual Studio 2017 Enterprise). Cambie este valor según la ubicación de instalación, la edición y la versión de Visual Studio.

7. Elija un valor para el campo **Directorio inicial**, como **Directorio del proyecto**.

8. Elija el botón **Aceptar** .

   Se agregará el nuevo elemento de menú y podrá acceder al símbolo del sistema desde el menú **Herramientas**.

## <a name="see-also"></a>Vea también

- [Herramientas](../../../docs/framework/tools/index.md)
- [Administrar herramientas externas](/visualstudio/ide/managing-external-tools)
