---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 54d438541e8840e4394b24b20b4f394ff8cdb820
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788952"
---
# <a name="-optionexplicit"></a>-optionexplicit
Hace que el compilador notifique errores si no se declaran las variables antes de utilizarlas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. Especificar `-optionexplicit+` para requerir la declaración explícita de variables. El `-optionexplicit+` opción es el valor predeterminado y es el mismo que `-optionexplicit`. El `-optionexplicit-` opción permite la declaración implícita de variables.  
  
## <a name="remarks"></a>Comentarios  
 Si el archivo de código fuente contiene un [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la instrucción invalida el `-optionexplicit` configuración del compilador de línea de comandos.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Establecer - optionexplicit en el IDE de Visual Studio  
  
1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.   
  
2. Haga clic en la pestaña **Compilar**.  
  
3. Modifique el valor en el **Option Explicit** cuadro.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila cuando `-optionexplicit-` se utiliza.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
