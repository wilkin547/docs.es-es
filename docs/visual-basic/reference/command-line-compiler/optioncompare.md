---
title: /optioncompare | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
dev_langs:
- VB
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 53dee5bb50e20204725f031e3e04f5c37c5b3f96
ms.lasthandoff: 03/13/2017

---
# <a name="optioncompare"></a>/optioncompare
Especifica la forma en que se realizan las comparaciones de cadenas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede especificar `/optioncompare` en uno de dos formas: `/optioncompare:binary` usar comparaciones de cadenas binarias y `/optioncompare:text` para utilizar comparaciones de cadenas de texto. De forma predeterminada, el compilador utiliza `/optioncompare:binary`.  
  
 En Microsoft Windows, la página de códigos que se utiliza determina el criterio de ordenación binario. Un criterio de ordenación binario típico es el siguiente:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Comparaciones de cadenas de texto se basan en un criterio de ordenación de texto entre mayúsculas y minúsculas determinado por la configuración regional del sistema. Un criterio de ordenación de texto habitual es la siguiente:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a>Para establecer /optioncompare en el IDE de Visual Studio  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en el **compilar** ficha.  
  
3.  Modifique el valor en el **Option Compare** cuadro.  
  
### <a name="to-set-optioncompare-programmatically"></a>Para establecer /optioncompare mediante programación  
  
-   Consulte [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila P`rojFile.vb` y usa comparaciones de cadenas binarias.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
