---
title: El nombre <namespacename> del espacio de nombres raíz <fullnamespacename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 4e29a27841021b0cf68af01f4535e60eeb38b9a8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871515"
---
# <a name="name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a>El nombre \<namespacename> del espacio de nombres raíz \<fullnamespacename> no es compatible con CLS

Un ensamblado está marcado como `<CLSCompliant(True)>` , pero un elemento del nombre del espacio de nombres raíz comienza con un carácter de subrayado ( `_` ).  
  
 Un elemento de programación puede contener uno o más guiones bajos, pero para que sea compatible con la [independencia del lenguaje y los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40039  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si requiere la conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comience con un carácter de subrayado.  
  
- Si requiere que el nombre del espacio de nombres permanezca inalterado, quite el del <xref:System.CLSCompliantAttribute> ensamblado o márquelo como `<CLSCompliant(False)>` .  
  
## <a name="see-also"></a>Consulte también

- [Namespace (Instrucción)](../statements/namespace-statement.md)
- [Espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [-rootnamespace](../../reference/command-line-compiler/rootnamespace.md)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Convenciones de nomenclatura de Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
