---
title: "S&#237;mbolo del sistema para desarrolladores de Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "símbolo del sistema, Windows SDK"
  - "Visual Studio (símbolo del sistema)"
  - "símbolo del sistema, Visual Studio"
  - "SDK (símbolo del sistema)"
  - "herramientas [.NET Framework], establecer variables de entorno"
  - "variables de entorno, establecer para herramientas"
  - "símbolo del sistema para desarrolladores"
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
caps.latest.revision: 45
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 45
---
# S&#237;mbolo del sistema para desarrolladores de Visual Studio
El símbolo del sistema para desarrolladores de Visual Studio establece automáticamente las variables de entorno que permiten usar fácilmente las herramientas de .NET Framework. El símbolo del sistema para desarrolladores se instala con la edición completa o la edición Community de Visual Studio. No se instala con las versiones Express de Visual Studio.  
  
<a name="find"></a>   
## Buscar el símbolo del sistema en el equipo  
 Quizás vea varios símbolos del sistema, dependiendo de la versión de Visual Studio y de los SDK adicionales que haya instalado. Por ejemplo, las versiones de 64 bits de Visual Studio proporcionan los símbolos del sistema de 32 y de 64 bits. \(Las versiones de 32 y 64 bits de la mayoría de las herramientas son idénticas; sin embargo, algunas herramientas realizan cambios específicos para los entornos de 32 o 64 bits\). Si estos pasos no funcionan, puede intentar [Buscar manualmente los archivos en el equipo](#alternative) o [Ejecutar el símbolo del sistema desde Visual Studio](#visualstudio).  
  
 **En Windows 10**  
  
1.  Abra el menú **Inicio** presionando la tecla del logotipo de Windows ![Logotipo de Windows](../../../docs/framework/install/media/windowskeyboardlogo.png "Windowskeyboardlogo") en el teclado.  
  
2.  En el menú **Inicio**, escriba `des`. Esto mostrará una lista de las aplicaciones instaladas que coinciden con el patrón de búsqueda. Si está buscando un símbolo del sistema diferente, pruebe a escribir un término de búsqueda diferente como `símbolo`.  
  
3.  Elija el **Símbolo del sistema para desarrolladores** \(o el símbolo que quiera usar\).  
  
 **En Windows 8.1**  
  
1.  Vaya a la pantalla **Inicio** presionando la tecla del logotipo de Windows ![Logotipo de Windows](../../../docs/framework/install/media/windowskeyboardlogo.png "Windowskeyboardlogo") en el teclado.  
  
2.  En la pantalla **Inicio**, presione `CTRL + TAB` para abrir la lista **Aplicaciones** y escriba `V`. Esto mostrará una lista que incluye los símbolos del sistema de Visual Studio instalados.  
  
3.  Elija el **Símbolo del sistema para desarrolladores** \(o el símbolo que quiera usar\).  
  
 **En Windows 8**  
  
1.  Vaya a la pantalla **Inicio** presionando la tecla del logotipo de Windows ![Logotipo de Windows](../../../docs/framework/install/media/windowskeyboardlogo.png "Windowskeyboardlogo") en el teclado.  
  
2.  En la pantalla **Inicio**, presione la tecla con el logotipo de Windows ![Logotipo de Windows](../../../docs/framework/install/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.  
  
3.  Elija el icono **Vista Aplicaciones** en la parte inferior de la pantalla y después escriba `V`. Esto mostrará una lista que incluye los símbolos del sistema de Visual Studio instalados.  
  
4.  Elija el **Símbolo del sistema para desarrolladores** \(o el símbolo que quiera usar\).  
  
 **En Windows 7**  
  
1.  Elija **Inicio**, expanda **Todos los programas** y, después, expanda **Microsoft Visual Studio**.  
  
2.  Según la versión de Visual Studio que tenga instalada, elija **Visual Studio Tools**, **Visual Studio Command Prompt** o el símbolo del sistema que quiere usar.  
  
 Si tiene [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) o [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) instalado, puede ver símbolos del sistema adicionales para las arquitecturas ARM, x86 o x64. Consulte la documentación de cada herramienta para conocer la versión del símbolo del sistema que debe utilizar.  
  
<a name="alternative"></a>   
## Buscar manualmente los archivos en el equipo  
  Normalmente, los accesos directos de los símbolos del sistema que haya instalado se colocan en la carpeta **Menú Inicio** para Visual Studio; por ejemplo, en C:\\ProgramData\\Microsoft\\Windows\\Menú Inicio\\Programas\\Visual Studio 2015\\Visual Studio Tools.    Pero si por alguna razón, la búsqueda del símbolo del sistema no muestra los resultados esperados, puede intentar buscar manualmente el acceso directo en el equipo para poder usarlo.   Pruebe a buscar el nombre del archivo de símbolo del sistema; por ejemplo, VsDevCmd.bat o vaya a la carpeta de herramientas; por ejemplo, C:\\Program Files \(x 86\) \\Microsoft Visual Studio 14.0\\Common7\\Tools \(la ruta de acceso cambia según la versión de Visual Studio y la ubicación de instalación\).  
  
<a name="visualstudio"></a>   
## Ejecutar el símbolo del sistema desde Visual Studio  
 Para un acceso más sencillo, puede agregar el símbolo del sistema para desarrolladores de Visual Studio o cualquier otro símbolo del sistema al menú Herramientas de Visual Studio con tan solo agregarlo a la lista de herramientas externas. Haga lo siguiente:  
  
1.  Abra Visual Studio.  
  
2.  Seleccione el menú **Herramientas** y elija **Herramientas externas...**.  
  
3.  En el cuadro de diálogo **Herramientas externas**, elija el botón **Agregar**. Aparecerá una nueva entrada.  
  
4.  Escriba el **Título** correspondiente al nuevo elemento de menú \(por ejemplo, `Símbolo del sistema`.  
  
5.  En el campo **Comando** indique el archivo que desea iniciar como, por ejemplo, `%comspec%` o `C:\Windows\System32\cmd.exe`.  
  
6.  En el campo **Argumentos** indique dónde se encuentra el símbolo del sistema específico que quiere usar como, por ejemplo, `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` \(esto iniciará el símbolo del sistema para desarrolladores instalado con [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]\). Es necesario cambiar este valor según la ubicación de instalación y la versión de Visual Studio.  
  
7.  Elija un valor para el campo **Directorio inicial** \(por ejemplo, **Directorio del proyecto**\).  
  
8.  Elija el botón **Aceptar**.  
  
 De este modo, se agregará el nuevo elemento de menú y ya podrá acceder al símbolo del sistema desde el menú **Herramientas**.  
  
## Vea también  
 [Tools](../../../docs/framework/tools/index.md)   
 [Administrar herramientas externas](../Topic/Managing%20External%20Tools.md)