---
description: 'Más información sobre: BC40039: el nombre del <namespacename> espacio de nombres raíz <fullnamespacename> no es conforme a CLS'
title: El nombre <namespacename> del espacio de nombres raíz <fullnamespacename> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40039
- bc40039
helpviewer_keywords:
- BC40039
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
ms.openlocfilehash: 2560c5c056c70909a08a48a0ff8b2859b178cc8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795734"
---
# <a name="bc40039-name-namespacename-in-the-root-namespace-fullnamespacename-is-not-cls-compliant"></a>BC40039: el nombre del \<namespacename> espacio de nombres raíz \<fullnamespacename> no es conforme a CLS

Un ensamblado está marcado como `<CLSCompliant(True)>` , pero un elemento del nombre del espacio de nombres raíz comienza con un carácter de subrayado ( `_` ).

 Un elemento de programación puede contener uno o más subrayados, pero para ser compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.

 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.

 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC40039

## <a name="to-correct-this-error"></a>Para corregir este error

- Si requiere la conformidad con CLS, cambie el nombre del espacio de nombres raíz para que ninguno de sus elementos comience con un carácter de subrayado.

- Si requiere que el nombre del espacio de nombres permanezca inalterado, quite el del <xref:System.CLSCompliantAttribute> ensamblado o márquelo como `<CLSCompliant(False)>` .

## <a name="see-also"></a>Vea también

- [Namespace (Instrucción)](../statements/namespace-statement.md)
- [Espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [-rootnamespace](../../reference/command-line-compiler/rootnamespace.md)
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Convenciones de nomenclatura de Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
