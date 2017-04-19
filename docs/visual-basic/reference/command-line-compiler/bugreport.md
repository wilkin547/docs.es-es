---
title: / bugreport | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9c64ec49d7e6842edbc0fed7407a34132a8f5a88
ms.lasthandoff: 03/13/2017

---
# <a name="bugreport"></a>/bugreport
Crea un archivo que puede utilizar cuando el archivo de un informe de errores.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`file`|Obligatorio. El nombre del archivo que contendrá el informe de error. Encierre el nombre de archivo entre comillas ("") si el nombre contiene un espacio.|  
  
## <a name="remarks"></a>Comentarios  
 La siguiente información se agrega a `file`:  
  
-   Una copia de todos los archivos de código fuente en la compilación.  
  
-   Una lista de las opciones del compilador utilizadas en la compilación.  
  
-   Información de versión sobre el compilador, el common language runtime y el sistema operativo.  
  
-   Resultados del compilador, si existe.  
  
-   Una descripción del problema, para el que se le solicite.  
  
-   Una descripción de cómo piensa que el problema debe corregirse para que le pedirá.  
  
 Dado que una copia de todos los archivos de código fuente se incluye en `file`, desea reproducir el defecto de código (sospechado) en el programa más corto posible.  
  
> [!IMPORTANT]
>  El `/bugreport` opción genera un archivo que contiene información potencialmente confidencial. Esto incluye la hora actual, versión del compilador, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] versión, versión del sistema operativo, nombre de usuario, los argumentos de línea de comandos con la que se ejecutó el compilador, todo el código fuente y la forma binaria de cualquier ensamblado de referencia. Esta opción puede obtenerse mediante la especificación de opciones de línea de comandos en el archivo Web.config para una compilación de servidor de un [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] aplicación. Para evitar esto, modifique el archivo Machine.config para impedir que los usuarios puedan compilar en el servidor.  
  
 Si esta opción se utiliza con `/errorreport:prompt`, `/errorreport:queue`, o `/errorreport:send`, y la aplicación detecta un error interno del compilador, la información de `file` se envía a Microsoft Corporation. Esta información le ayudará a los ingenieros de Microsoft a identificar la causa del error y puede ayudar a mejorar la siguiente versión de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. De forma predeterminada, no se envía información a Microsoft. Sin embargo, cuando se compila una aplicación con `/errorreport:queue`, que está habilitada de forma predeterminada, la aplicación recopila los informes de errores. A continuación, cuando el administrador del equipo inicia sesión, el sistema de informes de errores muestra una ventana emergente que permite al administrador reenviar a Microsoft los informes de errores que se produjeron desde el inicio de sesión.  
  
> [!NOTE]
>  El `/bugreport` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se compila `T2.vb` y coloca la información de todos los errores en el archivo `Problem.txt`.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Elemento trustLevel para securityPolicy (esquema de configuración de ASP.NET)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)
