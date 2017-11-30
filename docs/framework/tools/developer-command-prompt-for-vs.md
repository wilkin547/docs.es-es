---
title: "Símbolo del sistema para desarrolladores de Visual Studio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
caps.latest.revision: "45"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e93a1d116ac0480c80e259ddbadbc65fd9539389
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="developer-command-prompt-for-visual-studio"></a>Símbolo del sistema para desarrolladores de Visual Studio
El símbolo del sistema para desarrolladores de Visual Studio establece automáticamente las variables de entorno que permiten usar fácilmente las herramientas de .NET Framework. El símbolo del sistema para desarrolladores se instala con la edición completa o la edición Community de Visual Studio. No se instala con las versiones Express de Visual Studio.  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a>Buscar el símbolo del sistema en el equipo  
 Quizás vea varios símbolos del sistema, dependiendo de la versión de Visual Studio y de los SDK adicionales que haya instalado. Por ejemplo, las versiones de 64 bits de Visual Studio proporcionan los símbolos del sistema de 32 y de 64 bits. (Las versiones de 32 y 64 bits de la mayoría de las herramientas son idénticas; sin embargo, algunas herramientas realizan cambios específicos para los entornos de 32 o 64 bits). Si los pasos siguientes no funcionan, puede probar los indicados en [Buscar manualmente los archivos en la máquina](#alternative) o [Ejecutar el símbolo del sistema desde Visual Studio](#visualstudio).  
  
 **En Windows 10**  
  
1.  Abra el menú **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.  
  
2.  En el menú **Inicio**, escriba `dev`. Esto mostrará una lista de las aplicaciones instaladas que coinciden con el patrón de búsqueda. Si busca un símbolo del sistema diferente, pruebe a escribir otro término de búsqueda, como `prompt`.  
  
3.  Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).  
  
 **En Windows 8.1**  
  
1.  Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.  
  
2.  En la pantalla **Inicio**, presione `CTRL + TAB` para abrir la lista **Aplicaciones** y escriba `V`. Esto mostrará una lista que incluye los símbolos del sistema de Visual Studio instalados.  
  
3.  Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).  
  
 **En Windows 8**  
  
1.  Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.  
  
2.  En la pantalla **Inicio**, presione la tecla del logotipo de Windows ![logotipo de Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.  
  
3.  Elija el icono **Vista Aplicaciones** en la parte inferior de la pantalla y después escriba `V`. Esto mostrará una lista que incluye los símbolos del sistema de Visual Studio instalados.  
  
4.  Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).  
  
 **En Windows 7**  
  
1.  Elija **Inicio**, expanda **Todos los programas** y luego, **Microsoft Visual Studio**.  
  
2.  Según la versión de Visual Studio que tenga instalada, elija **Visual Studio Tools**, **Visual Studio Command Prompt** o el símbolo del sistema que quiera usar.  
  
 Si tiene [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) o [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) instalado, puede ver otros símbolos del sistema para las arquitecturas ARM, x86 o x64. Consulte la documentación de cada herramienta para conocer la versión del símbolo del sistema que debe utilizar.  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a>Buscar manualmente los archivos en el equipo  
  Normalmente, los accesos directos de los símbolos del sistema que haya instalado se colocan en la carpeta **Menú Inicio** para Visual Studio; por ejemplo, en C:\ProgramData\Microsoft\Windows\Menú Inicio\Programas\Visual Studio 2015\Visual Studio Tools.    Pero si por alguna razón, la búsqueda del símbolo del sistema no muestra los resultados esperados, puede intentar buscar manualmente el acceso directo en el equipo para poder usarlo.   Pruebe a buscar el nombre del archivo de símbolo del sistema; por ejemplo, VsDevCmd.bat o vaya a la carpeta de herramientas; por ejemplo, C:\Program Files (x 86) \Microsoft Visual Studio 14.0\Common7\Tools (la ruta de acceso cambia según la versión de Visual Studio y la ubicación de instalación).  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a>Ejecutar el símbolo del sistema desde Visual Studio  
 Para un acceso más sencillo, puede agregar el símbolo del sistema para desarrolladores de Visual Studio o cualquier otro símbolo del sistema al menú Herramientas de Visual Studio con tan solo agregarlo a la lista de herramientas externas. Haga lo siguiente:  
  
1.  Abra Visual Studio.  
  
2.  Seleccione el menú **Herramientas** y elija **Herramientas externas...**.  
  
3.  En el cuadro de diálogo **Herramientas externas**, elija el botón **Agregar**. Aparecerá una nueva entrada.  
  
4.  Escriba el **Título** correspondiente al nuevo elemento de menú (por ejemplo, `Command Prompt`).  
  
5.  Indique en el campo **Comando** el archivo que quiere iniciar como, por ejemplo, `%comspec%` o `C:\Windows\System32\cmd.exe`.  
  
6.  En el campo **Argumentos** indique dónde se encuentra el símbolo del sistema específico que quiere usar como, por ejemplo, `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (esto iniciará el símbolo del sistema para desarrolladores instalado con [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]). Es necesario cambiar este valor según la ubicación de instalación y la versión de Visual Studio.  
  
7.  Elija un valor para el campo **Directorio inicial** (por ejemplo, **Directorio del proyecto**).  
  
8.  Elija el botón **Aceptar** .  
  
 De este modo, se agregará el nuevo elemento de menú y ya podrá acceder al símbolo del sistema desde el menú **Herramientas**.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas](../../../docs/framework/tools/index.md)  
 [Administrar herramientas externas](/visualstudio/ide/managing-external-tools)
