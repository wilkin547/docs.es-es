---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: 3edb1f74ab63497aeda0d72847bce92ad315a1a5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098922"
---
# <a name="-optioninfer"></a>-optioninfer

Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. Especifique `-optioninfer+` para habilitar la inferencia de tipo de variable local o `-optioninfer-` para bloquearla. La opción `-optioninfer`, sin ningún valor especificado, es igual a `-optioninfer+`. El valor predeterminado cuando el modificador `-optioninfer` no está presente también es `-optioninfer+`. El valor predeterminado se establece en el archivo de respuesta vbc.rsp.|  
  
> [!NOTE]
> Puede utilizar la opción `-noconfig` para conservar los valores predeterminados internos del compilador en lugar de los especificados en vbc.rsp. El valor predeterminado del compilador para esta opción es `-optioninfer-`.  
  
## <a name="remarks"></a>Comentarios  

 Si el archivo de código fuente contiene una [instrucción Option Infer](../../language-reference/statements/option-infer-statement.md), la declaración reemplaza la configuración `-optioninfer` del compilador de la línea de comandos.  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a>Para establecer -optioninfer en el IDE de Visual Studio  
  
1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.  
  
2. En la pestaña **Compilar**, modifique el valor del cuadro **Option infer**.  
  
## <a name="example"></a>Ejemplo  

 El siguiente código compila `test.vb` con la inferencia de tipo de variable local habilitada.  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-optioncompare](optioncompare.md)
- [-optionexplicit](optionexplicit.md)
- [-optionstrict](optionstrict.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Option Infer (instrucción)](../../language-reference/statements/option-infer-statement.md)
- [Inferencia de tipo de variable local](../../programming-guide/language-features/variables/local-type-inference.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [Página Compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [-noconfig](noconfig.md)
- [Compilación desde la línea de comandos](building-from-the-command-line.md)
