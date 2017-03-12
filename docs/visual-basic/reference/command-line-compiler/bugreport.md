---
title: "/bugreport | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/bugreport (opción del compilador) [Visual Basic]"
  - "bugreport (opción del compilador) [Visual Basic]"
  - "-bugreport (opción del compilador) [Visual Basic]"
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# /bugreport
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Crea un archivo que se puede usar para almacenar un informe de error.  
  
## Sintaxis  
  
```  
/bugreport:file  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`file`|Obligatorio.  Nombre del archivo que va a contener el informe de error.  Escriba el nombre de archivo entre comillas \(" "\) si contiene espacios.|  
  
## Comentarios  
 Se agrega a `file` la información siguiente:  
  
-   Una copia de todos los archivos de código fuente de la compilación.  
  
-   Una lista de las opciones del compilador utilizadas en la compilación.  
  
-   Información de versión acerca del compilador, Common Language Runtime y sistema operativo utilizados.  
  
-   Resultados del compilador, si existen.  
  
-   Descripción del problema, que debe rellenar el usuario.  
  
-   Descripción de cómo se debería resolver el problema, que debe rellenar el usuario.  
  
 Dado que se incluye una copia de todos los archivos de código fuente en `file`, se recomienda reproducir el defecto de código \(que se sospecha\) en el programa más corto posible.  
  
> [!IMPORTANT]
>  La opción `/bugreport` genera un archivo que contiene potencialmente información confidencial.  Entre ella se incluye la hora actual, la versión del compilador, la versión de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], la versión del sistema operativo, el nombre de usuario, los argumentos de la línea de comandos con que se ejecutó el compilador, todo el código fuente y el formato binario de los ensamblados a que se hace referencia.  Para tener acceso a esta opción es necesario especificar opciones de línea de comandos en el archivo Web.config para una compilación de servidor de una aplicación [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)].  Para evitar esto, modifique el archivo Machine.config para que los usuarios no puedan compilar en el servidor.  
  
 Si se utiliza esta opción con `/errorreport:prompt`, `/errorreport:queue` o `/errorreport:send` y la aplicación detecta un error del compilador interno, la información incluida en `file` se envía a Microsoft Corporation.  Esta información ayudará a los ingenieros de Microsoft a identificar la causa del error y puede ayudar a mejorar la siguiente versión de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  De manera predeterminada, no se envía información a Microsoft.  Sin embargo, cuando se compila una aplicación utilizando `/errorreport:queue`, que está habilitado de forma predeterminada, la aplicación recopila los informes de errores.  Entonces, cuando el administrador del equipo inicia una sesión, el sistema de notificación de errores muestra una ventana emergente que permite al administrador reenviar a Microsoft los informes de errores que se hayan generado desde el inicio de la sesión.  
  
> [!NOTE]
>  La opción `/bugreport` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 En el  siguiente ejemplo de código se compila `T2.vb` y se incluye toda la información de errores en el archivo `Problem.txt`:  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [\/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Elemento trustLevel para securityPolicy \(Esquema de configuración de ASP.NET\)](http://msdn.microsoft.com/es-es/729ab04c-03da-4ee5-86b1-be9d08a09369)