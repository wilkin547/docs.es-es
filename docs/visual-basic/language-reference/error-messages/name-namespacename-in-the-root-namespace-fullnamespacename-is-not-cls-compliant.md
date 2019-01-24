---
title: Nombre &lt;namespacename&gt; en el espacio de nombres raíz &lt;fullnamespacename&gt; no es conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 8d35268891711ca7f2a7f5ec47be425e342dccd7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642534"
---
# <a name="name-ltnamespacenamegt-in-the-root-namespace-ltfullnamespacenamegt-is-not-cls-compliant"></a>Nombre &lt;namespacename&gt; en el espacio de nombres raíz &lt;fullnamespacename&gt; no es conforme a CLS
Un ensamblado está marcado como `<CLSCompliant(True)>`, pero un elemento del nombre de espacio de nombres raíz comienza con un carácter de subrayado (`_`).  
  
 Un elemento de programación puede contener uno o más caracteres de subrayado, pero to sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40039  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si requiere conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comienza con un carácter de subrayado.  
  
-   Si necesita que el espacio de nombres permanecen sin cambios, a continuación, quite el <xref:System.CLSCompliantAttribute> desde el ensamblado o márquelo como `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Vea también
- [Namespace (instrucción)](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)

