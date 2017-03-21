---
title: / main | Documentos de Microsoft
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
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: dded7621845141896f353d69ab757010c825b975
ms.lasthandoff: 03/13/2017

---
# <a name="main"></a>/main
Especifica la clase o módulo que contiene el `Sub Main` procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/main:location  
```  
  
## <a name="arguments"></a>Argumentos  
 `location`  
 Obligatorio. Una especificación completa de la clase o módulo que contiene el `Sub Main` procedimiento al que llamar cuando se inicia el programa. Esto puede ser en forma **/main:module** o **Module**.  
  
## <a name="remarks"></a>Comentarios  
 Utilice esta opción cuando se crea un archivo ejecutable o un programa ejecutable de Windows. Si el **/main** se omite la opción, el compilador busca válido compartido `Sub Main` en todas las clases y módulos públicos.  
  
 Consulte [procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) para obtener una explicación de las distintas formas de la `Main` procedimiento.  
  
 Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un valor predeterminado `Main` procedimiento que inicia la aplicación si la clase no tiene ningún `Main` procedimiento.</xref:System.Windows.Forms.Form> Esto le permite compilar el código en la línea de comandos que se creó en el entorno de desarrollo.  
  
 [!code-vb[VbVbalrCompiler Nº&16;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set-main-in-the-visual-studio-integrated-development-environment"></a>Para establecer /main en Visual Studio de entorno de desarrollo integrado  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**.  
  
     Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la pestaña **Aplicación** .  
  
3.  Asegúrese de que el **activar marco de aplicación** casilla de verificación no está activada.  
  
4.  Modifique el valor en el **objeto Startup** cuadro.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y `T3.vb`, especificando que la `Sub Main` procedimiento se encuentra en la `Test2` clase.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [NIB: versión de Visual Basic de Hola a todos](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)   
 [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
