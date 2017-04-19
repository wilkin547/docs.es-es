---
title: /define (Visual Basic) | Documentos de Microsoft
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
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: 15
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
ms.openlocfilehash: 48c3bae1c6cf5831f95ce86dbcf6adadab9d5db8
ms.lasthandoff: 03/13/2017

---
# <a name="define-visual-basic"></a>/define (Visual Basic)
Permite definir constantes condicionales para el compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`symbol`|Requerido. Símbolo que se va a definir.|  
|`value`|Opcional. Valor que se va a asignar a `symbol`. Si `value` es una cadena, debe incluirse entre secuencias de barra diagonal inversa/comillas (\\") en lugar de comillas. Si no se especifica ningún valor, se considera como verdadero.|  
  
## <a name="remarks"></a>Comentarios  
 La opción `/define` tiene un efecto similar a usar una directiva de preprocesador `#Const` en el archivo de origen, salvo por el hecho de que las constantes con `/define` son públicas y se aplican a todos los archivos del proyecto.  
  
 Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.  
  
 `/d` es la forma abreviada de `/define`.  
  
 Se pueden definir varios símbolos con `/define`; use una coma para separar las definiciones de símbolos.  
  
|Para definir/establecer en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **compilar** ficha.<br />3.  Haga clic en **Avanzado**.<br />4.  Modifique el valor en el **constantes personalizadas** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente código se definen y usan dos constantes de compilador condicionales.  
  
 [!code-vb[VbVbalrCompiler nº&45;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [#If... Then... #Else directivas](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
