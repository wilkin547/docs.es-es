---
description: "Más información acerca de: BC40057: el espacio de nombres o tipo especificado en las importaciones de nivel de proyecto ' <qualifiedelementname> ' no contiene ningún miembro público o no se encuentra"
title: El espacio de nombres o tipo especificado en las importaciones del proyecto '<qualifiedelementname>' no tiene miembros públicos o no se encuentra
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 66ae40ca6a2feff78f80bdbc8886387e801f7db2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795695"
---
# <a name="bc40057-namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>BC40057: el espacio de nombres o tipo especificado en las importaciones de nivel de proyecto ' \<qualifiedelementname> ' no contiene ningún miembro público o no se encuentra.

El espacio de nombres o tipo especificado en las importaciones de nivel de proyecto ' \<qualifiedelementname> ' no contiene ningún miembro público o no se encuentra. Asegúrese de que el espacio de nombres o el tipo estén definidos y que contenga al menos un miembro público. Asegúrese de que el nombre de alias no contenga otros alias.

 Una propiedad Import de un proyecto especifica un elemento contenedor que no se puede encontrar o no define ningún `Public` miembro.

 Un *elemento contenedor* puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz o una enumeración. El elemento contenedor contiene miembros, como variables, procedimientos u otros elementos contenedores.

 El propósito de la importación es permitir que el código tenga acceso a los miembros de espacio de nombres o de tipo sin tener que calificarlos. Es posible que el proyecto también tenga que agregar una referencia al espacio de nombres o al tipo. Para obtener más información, vea "importar elementos contenedores" en [referencias a elementos declarados](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

 Si el compilador no encuentra el elemento contenedor especificado, no puede resolver las referencias que lo usan. Si encuentra el elemento pero el elemento no expone ningún `Public` miembro, no se puede realizar ninguna referencia correctamente. En cualquier caso, no tiene sentido importar el elemento.

 El diseñador de **proyectos** se usa para especificar los elementos que se van a importar. Use la sección **espacios de nombres importados** de la página **referencias** . Para obtener acceso al **Diseñador de proyectos** , haga doble clic en el icono **mi proyecto** en **Explorador de soluciones**.

 **Identificador de error:** BC40057

## <a name="to-correct-this-error"></a>Para corregir este error

1. Abra el **Diseñador de proyectos** y cambie a la página de **referencia** .

2. En la sección **espacios de nombres importados** , compruebe que el elemento contenedor es accesible desde el proyecto.

3. Compruebe que el elemento contenedor expone al menos un `Public` miembro.

## <a name="see-also"></a>Consulte también

- [Página Referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Público](../modifiers/public.md)
- [Espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
