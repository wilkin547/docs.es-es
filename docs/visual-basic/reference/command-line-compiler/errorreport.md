---
title: /errorreport | Documentos de Microsoft
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
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ebe5646256926f68a1a900b91c25a1768505785
ms.lasthandoff: 03/13/2017

---
# <a name="errorreport"></a>/errorreport
Especifica cómo debe documentar el compilador [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] los errores internos del compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a>Comentarios  
 Esta opción proporciona una manera cómoda de informe una [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] error interno del compilador (ICE) a la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] team en Microsoft. De forma predeterminada, el compilador no envía ninguna información a Microsoft. Sin embargo, si se produce un error de compilador interno, esta opción permite informar del error a Microsoft. Esta información le ayudará a los ingenieros de Microsoft a identificar la causa y puede ayudar a mejorar la siguiente versión de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Capacidad de un usuario para enviar informes depende de permisos de la directiva de equipo y usuario.  
  
 En la tabla siguiente se resume el efecto de la `/errorreport` opción.  
  
|Opción|Comportamiento|  
|---|---|  
|`prompt`|Si se produce un error interno del compilador, aparece un cuadro de diálogo para que pueda ver los datos exactos que recogidos por el compilador. Puede determinar si hay cualquier información confidencial en el informe de errores y tomar una decisión sobre si se envía a Microsoft. Si decide enviarlo, y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.|  
|`queue`|Pone en cola el informe de errores. Cuando inicie sesión con privilegios de administrador, puede notificar los errores desde la última vez que inició sesión (no se le para enviar informes de errores más de una vez cada tres días). Este es el comportamiento predeterminado cuando la `/errorreport` no se especifica la opción.|  
|`send`|Si se produce un error interno del compilador, y la configuración de directiva de equipo y de usuario lo permite, el compilador envía los datos a Microsoft.<br /><br /> La opción `/errorReport:send` intenta enviar automáticamente información de errores a Microsoft. Esta opción depende del registro. Para obtener más información acerca de cómo establecer los valores apropiados en el registro, consulte [cómo activar el informe de errores automático en las herramientas de línea de comandos de Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).|  
|`none`|Si se produce un error interno del compilador, no se recopila o envía a Microsoft.|  
  
 El compilador envía datos que incluyen la pila en el momento del error, que normalmente incluye algún código fuente. Si `/errorreport` se usa con el [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, se envía el archivo de código fuente completo.  
  
 Esta opción se usa mejor con la [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opción, ya que permite a los ingenieros de Microsoft más fácil reproducen el error.  
  
> [!NOTE]
>  El `/errorreport` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente intenta compilar `T2.vb`, y si el compilador encuentra un error interno del compilador, le pide que enviar el informe de errores a Microsoft.  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
