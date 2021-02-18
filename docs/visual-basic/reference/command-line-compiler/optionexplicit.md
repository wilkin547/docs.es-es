---
description: Mas información sobre -optionexplicit
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
ms.openlocfilehash: 4d1ab14bbf9de176de17fb5077f4bb919f5472b4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433567"
---
# <a name="-optionexplicit"></a>-optionexplicit

Hace que el compilador notifique errores si las variables no se declaran antes de usarlas.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  

 `+` &#124; `-`  
 Opcional. Especifique `-optionexplicit+` para requerir la declaración explícita de variables. La opción `-optionexplicit+` es el valor predeterminado y es igual a `-optionexplicit`. La opción `-optionexplicit-` habilita la declaración implícita de variables.  
  
## <a name="remarks"></a>Comentarios  

 Si el archivo de código fuente contiene una [instrucción Option Explicit](../../language-reference/statements/option-explicit-statement.md), la declaración reemplaza el valor `-optionexplicit` del compilador de la línea de comandos.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>Para establecer -optionexplicit en el IDE de Visual Studio  
  
1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.
  
2. Haga clic en la pestaña **Compilar**.  
  
3. Modifique el valor del cuadro **Option Explicit**.  
  
## <a name="example"></a>Ejemplo  

 El código siguiente se compila cuando se usa `-optionexplicit-`.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-optioncompare](optioncompare.md)
- [-optionstrict](optionstrict.md)
- [-optioninfer](optioninfer.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Option Explicit (instrucción)](../../language-reference/statements/option-explicit-statement.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
