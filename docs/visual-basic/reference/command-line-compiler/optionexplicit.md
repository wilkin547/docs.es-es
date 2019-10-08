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
ms.openlocfilehash: 5c0946b94bfe02d797d1a484088869375703eb6a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005311"
---
# <a name="-optionexplicit"></a>-optionexplicit
Hace que el compilador notifique errores si las variables no se declaran antes de usarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. Especifique `-optionexplicit+` para requerir la declaración explícita de variables. La opción `-optionexplicit+` es el valor predeterminado y es igual que `-optionexplicit`. La opción `-optionexplicit-` habilita la declaración implícita de variables.  
  
## <a name="remarks"></a>Comentarios  
 Si el archivo de código fuente contiene una [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la instrucción reemplaza la configuración del compilador de línea de comandos `-optionexplicit`.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Para Set-OptionExplicit en el IDE de Visual Studio  
  
1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.   
  
2. Haga clic en la pestaña **Compilar**.  
  
3. Modifique el valor en el cuadro **Option Explicit** .  
  
## <a name="example"></a>Ejemplo  
 El siguiente código se compila cuando se usa `-optionexplicit-`.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
