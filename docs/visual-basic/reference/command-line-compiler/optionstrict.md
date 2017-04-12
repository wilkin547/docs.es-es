---
title: /optionstrict | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
dev_langs:
- VB
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
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
ms.openlocfilehash: 0394d9c1f4c082271316829ef1d226bd97d136c9
ms.lasthandoff: 03/13/2017

---
# <a name="optionstrict"></a>/optionstrict
Aplica la semántica de tipos estricta para restringir las conversiones implícitas de tipos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. El `/optionstrict+` opción restringe la conversión de tipos implícita. El valor predeterminado para esta opción es `/optionstrict-`. El `/optionstrict+` opción es el mismo que `/optionstrict`. Puede utilizar tanto para la semántica de tipos permisiva.  
  
 `custom`  
 Obligatorio. Advertir cuando no se respete la semántica estricta del lenguaje.  
  
## <a name="remarks"></a>Comentarios  
 Cuando `/optionstrict+` está en vigor, se pueden realizar conversiones de tipo de ampliación sólo implícitamente. Conversiones de tipos, como la asignación de restricción implícitas un `Decimal` escriba en un objeto de tipo entero, se notifican como errores.  
  
 Para generar advertencias para las conversiones de tipo de restricción implícitas, utilice `/optionstrict:custom`. Utilice `/nowarn:numberlist` para omitir advertencias determinadas y `/warnaserror:numberlist` para tratar determinadas advertencias como errores.  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a>Para establecer /optionstrict en el IDE de Visual Studio  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades.** Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en el **compilar** ficha.  
  
3.  Modifique el valor en el **Option Strict** cuadro.  
  
### <a name="to-set-optionstrict-programmatically"></a>Para establecer /optionstrict mediante programación  
  
-   Consulte [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `Test.vb` usando la semántica de tipos estricta.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)   
 [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
