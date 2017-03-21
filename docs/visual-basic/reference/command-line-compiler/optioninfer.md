---
title: /optioninfer | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioninfer
dev_langs:
- VB
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
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
ms.openlocfilehash: 0c0b6d8361e2bd59837161d1135b100e66d40887
ms.lasthandoff: 03/13/2017

---
# <a name="optioninfer"></a>/optioninfer
Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`+` &#124; `-`|Opcional. Especifique `/optioninfer+` para habilitar la inferencia de tipo de variable local o `/optioninfer-` para bloquearla. La opción `/optioninfer`, sin ningún valor especificado, es igual a `/optioninfer+`. El valor predeterminado cuando el modificador `/optioninfer` no está presente también es `/optioninfer+`. El valor predeterminado se establece en el archivo de respuesta vbc.rsp.|  
  
> [!NOTE]
>  Puede utilizar la opción `/noconfig` para conservar los valores predeterminados internos del compilador en lugar de los especificados en vbc.rsp. El valor predeterminado del compilador para esta opción es `/optioninfer-`.  
  
## <a name="remarks"></a>Comentarios  
 Si el archivo de código fuente contiene un [Option Infer instrucción](../../../visual-basic/language-reference/statements/option-infer-statement.md), la declaración reemplaza el `/optioninfer` configuración del compilador de línea de comandos.  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a>Cómo establecer /optioninfer en el IDE de Visual Studio  
  
1.  Seleccione un proyecto en **el Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [NIB: administrar propiedades del proyecto con el Diseñador de proyectos](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  En el **compilar** ficha, modifique el valor en el **Option infer** cuadro.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `test.vb` con la inferencia de tipo de variable local habilitada.  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Opción Infer (instrucción)](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Inferencia de tipo local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Cuadro de diálogo de opciones de valores predeterminados, proyectos, Visual Basic](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)   
 [Página Compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)   
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Compilación desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
