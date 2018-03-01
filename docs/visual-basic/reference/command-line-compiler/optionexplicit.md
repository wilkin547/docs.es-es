---
title: /optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1e701addb31b361e55f2761f441c23deaef7c10d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="optionexplicit"></a>/optionexplicit
Hace que el compilador para informar de errores si no se declaran variables antes de utilizarlos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. Especificar `/optionexplicit+` para requerir la declaración explícita de variables. El `/optionexplicit+` opción es el valor predeterminado y es el mismo que `/optionexplicit`. El `/optionexplicit-` opción habilita la declaración implícita de variables.  
  
## <a name="remarks"></a>Comentarios  
 Si el archivo de código fuente contiene un [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la instrucción anula la `/optionexplicit` configuración del compilador de línea de comandos.  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a>Para establecer /optionexplicit en el IDE de Visual Studio  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.   
  
2.  Haga clic en la pestaña **Compilar**.  
  
3.  Modifique el valor en el **Option Explicit** cuadro.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila cuando `/optionexplicit-` se utiliza.  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
