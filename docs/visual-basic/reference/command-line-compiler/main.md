---
title: -principal
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51a527dfddd2b78ac1c0559420298a66eb4b63f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652927"
---
# <a name="-main"></a>-principal
Especifica la clase o el módulo que contiene el procedimiento `Sub Main`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-main:location  
```  
  
## <a name="arguments"></a>Argumentos  
 `location`  
 Requerido. El nombre de la clase o módulo que contiene el `Sub Main` procedimiento al que llamar cuando se inicia el programa. Esto puede tener el formato **-main: module** o **-main:namespace.module**.  
  
## <a name="remarks"></a>Comentarios  
 Utilice esta opción cuando se crea un archivo ejecutable o un programa ejecutable de Windows. Si el **-principal** opción se omite, el compilador busca válido compartido `Sub Main` en todos los módulos y las clases públicas.  
  
 Vea [procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) para obtener una explicación de las distintas formas de la `Main` procedimiento.  
  
 Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un valor predeterminado `Main` procedimiento que inicia la aplicación si la clase no tiene ningún `Main` procedimiento. Esto le permite compilar el código en la línea de comandos que se creó en el entorno de desarrollo.  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>Para establecer - main en el entorno de desarrollo integrado de Visual Studio  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.  
  
2.  Haga clic en la pestaña **Aplicación** .  
  
3.  Asegúrese de que el **marco de aplicación de habilitar** no está activada la casilla de verificación.  
  
4.  Modifique el valor en el **objeto de inicio** cuadro.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y `T3.vb`, especificando que la `Sub Main` procedimiento se encuentra en la `Test2` clase.  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
