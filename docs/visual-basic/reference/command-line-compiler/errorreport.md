---
title: "/errorreport | Microsoft Docs"
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
  - "/errorreport (opción del compilador) [Visual Basic]"
  - "errorreport (opción del compilador) [Visual Basic]"
  - "-errorreport (opción del compilador) [Visual Basic]"
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /errorreport
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica cómo el compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] debe indicar los errores internos.  
  
## Sintaxis  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## Comentarios  
 Esta opción proporciona una forma cómoda de informar de un error interno del compilador \(ICE\) de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] al equipo de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] de Microsoft.  De manera predeterminada, el compilador no envía información a Microsoft.  Sin embargo, si encuentra un error del compilador interno, esta opción permite indicar el error a Microsoft.  Esta información ayudará a los ingenieros de Microsoft a identificar la causa y puede ayudar a mejorar la siguiente versión de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
 La capacidad de un usuario para enviar informes depende del equipo y de los permisos de la directiva del usuario.  
  
 En la tabla siguiente se resume el efecto de la opción `/errorreport`:  
  
|||  
|-|-|  
|Opción|Comportamiento|  
|`prompt`|Si se produce un error del compilador interno, aparece un cuadro de diálogo para que pueda ver los datos exactos recogidos por el compilador.  Puede determinar si hay cualquier información confidencial en el informe de errores y decidir si desea enviarlo a Microsoft.  Si decide enviarlo, y el equipo y configuración de la directiva de derechos de usuario lo permiten, el compilador envía los datos a Microsoft.|  
|`queue`|Pone en la cola el informe de errores.  Cuando inicia una sesión con privilegios de administrador, puede informar de todos los errores desde la última vez que inició una sesión \(se le pedirá que envíe informes de errores como máximo una vez cada tres días\).  Es el comportamiento predeterminado cuando no se especifica la opción `/errorreport`.|  
|`send`|Si se produce un error del compilador interno, y el equipo y configuración de la directiva de derechos de usuario lo permiten, el compilador envía los datos a Microsoft.<br /><br /> La opción `/errorReport:send` intenta enviar automáticamente información de error a Microsoft.  Esta opción depende del Registro.  Para obtener más información sobre la configuración de los valores en el Registro, vea [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command\-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).|  
|`none`|Si se produce un error del compilador interno, no se recopilará ni se enviará a Microsoft.|  
  
 El compilador envía datos que incluyen la pila en el momento del error, que normalmente incluye algún código fuente.  Si se utilizó `/errorreport` con la opción [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md), se envía todo el archivo de código fuente.  
  
 Esta opción se utiliza de manera más adecuada con la opción [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md), ya que permite a los ingenieros de Microsoft reproducir con más facilidad el error.  
  
> [!NOTE]
>  La opción `/errorreport` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 El código siguiente intenta compilar `T2.vb` y, si el compilador encuentra un error del compilador interno, pregunta si desea enviar el informe de errores a Microsoft.  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)