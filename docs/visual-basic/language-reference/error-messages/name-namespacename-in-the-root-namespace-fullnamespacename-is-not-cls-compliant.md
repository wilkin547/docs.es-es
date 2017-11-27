---
title: "Nombre &lt;namespacename&gt; en el espacio de nombres raíz &lt;fullnamespacename&gt; no es compatible con CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords: BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7342c7e85cce6c0e5892c4ad1826907dc03ed808
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a>Nombre &lt;namespacename&gt; en el espacio de nombres raíz &lt;fullnamespacename&gt; no es compatible con CLS
Un ensamblado está marcado como `<CLSCompliant(True)>`, pero un elemento del nombre de espacio de nombres raíz comienza con un carácter de subrayado (`_`).  
  
 Un elemento de programación puede contener uno o más caracteres de subrayado, pero to sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), no debe comenzar con un carácter de subrayado. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40039  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si necesita conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comienza con un carácter de subrayado.  
  
-   Si necesita que el espacio de nombres permanecen sin cambios, a continuación, quite el <xref:System.CLSCompliantAttribute> desde el ensamblado o márquelo como `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Vea también  
 [Namespace (instrucción)](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)  
 [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [\<PAVE sobre > escribir código conforme a CLS](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
