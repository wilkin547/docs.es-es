---
title: /bugreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7090142f940ae42f554fc0ba16bcc80d8537e38a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="bugreport"></a>/bugreport
Crea un archivo que puede utilizar cuando se archiva un informe de errores.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`file`|Obligatorio. El nombre del archivo que contendrá el informe de errores. Ponga el nombre de archivo entre comillas ("") si el nombre contiene un espacio.|  
  
## <a name="remarks"></a>Comentarios  
 La siguiente información se agrega a `file`:  
  
-   Una copia de todos los archivos de código fuente de la compilación.  
  
-   Una lista de las opciones del compilador utilizadas en la compilación.  
  
-   Información de versión sobre el compilador, el common language runtime y el sistema operativo.  
  
-   Resultados del compilador, si los hay.  
  
-   Una descripción del problema, para que se le pedirá.  
  
-   Una descripción de cómo cree que el problema debe corregirse para que se le pedirá.  
  
 Dado que una copia de todos los archivos de código fuente se incluye en `file`, puede que desee reproducir el defecto de código (que se sospecha) en el programa más corto posible.  
  
> [!IMPORTANT]
>  El `/bugreport` opción crea un archivo que contiene información potencialmente confidencial. Esto incluye la hora actual, versión del compilador, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] versión, versión del sistema operativo, nombre de usuario, los argumentos de línea de comandos con la que se ejecutó el compilador, todo el código fuente y el formato binario de cualquiera al que hace referencia el ensamblado. Esta opción puede obtenerse mediante la especificación de opciones de línea de comandos en el archivo Web.config para una compilación de servidor de un [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] aplicación. Para evitar esto, modifique el archivo Machine.config para no permitir a los usuarios de la compilación en el servidor.  
  
 Si esta opción se utiliza con `/errorreport:prompt`, `/errorreport:queue`, o `/errorreport:send`, y la aplicación encuentra un error interno del compilador, la información de `file` se envía a Microsoft Corporation. Esta información le ayudará a los ingenieros de Microsoft a identificar la causa del error y puede ayudar a mejorar la siguiente versión de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. De forma predeterminada, no se envía información a Microsoft. Sin embargo, cuando se compila una aplicación mediante el uso de `/errorreport:queue`, que está habilitada de forma predeterminada, la aplicación recopila los informes de errores. A continuación, cuando el administrador del equipo inicia una sesión, el sistema informes de errores muestra una ventana emergente que permite al administrador reenviar a Microsoft los informes de errores que se han realizado desde el inicio de sesión.  
  
> [!NOTE]
>  El `/bugreport` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se compila `T2.vb` y toda la información de notificación de los errores se incluye en el archivo `Problem.txt`.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Elemento de trustLevel para securityPolicy (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)
