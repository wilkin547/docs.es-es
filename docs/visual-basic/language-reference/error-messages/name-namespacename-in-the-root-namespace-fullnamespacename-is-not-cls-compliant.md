---
title: "Nombre &lt;namespacename&gt; en el espacio de nombres raíz &lt;fullnamespacename&gt; no es compatible con CLS | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
dev_langs:
- VB
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: 10
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
ms.openlocfilehash: 344a0ca098160a8d9f5bc8281a941311f82000c4
ms.lasthandoff: 03/13/2017

---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a>Nombre &lt;namespacename&gt; en el espacio de nombres raíz &lt;fullnamespacename&gt; no es compatible con CLS
Un ensamblado está marcado como `<CLSCompliant(True)>`, pero un elemento del nombre de espacio de nombres raíz comienza con un carácter de subrayado (`_`).  
  
 Un elemento de programación puede contener uno o más caracteres de subrayado, pero to sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), no debe comenzar con un carácter de subrayado. Consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Al aplicar el <xref:System.CLSCompliantAttribute>a un elemento de programación, establezca el atributo `isCompliant` parámetro como `True` o `False` para indicar compatibilidad o incompatibilidad.</xref:System.CLSCompliantAttribute> No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.  
  
 Si no se aplica el <xref:System.CLSCompliantAttribute>a un elemento, se considera como no conforme.</xref:System.CLSCompliantAttribute>  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40039  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si requiere compatibilidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comience con un carácter de subrayado.  
  
-   Si necesita que el espacio de nombres permanezca sin modificar, quitar el <xref:System.CLSCompliantAttribute>del ensamblado o márquelo como `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>Vea también  
 [Instrucción Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [/RootNamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)   
 [Página de aplicación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)   
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE sobre > escribir código conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
