---
title: El espacio de nombres o tipo especificado en las importaciones del proyecto '<qualifiedelementname>' no tiene miembros públicos o no se encuentra
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 105fa8da838938d13022c210c1f65cdafd251003
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308489"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Namespace o tipo especificado en el nivel de proyecto Imports'\<nombrecompletoelemento >' no contiene ningún miembro público o no se encuentra
Namespace o tipo especificado en el nivel de proyecto Imports'\<nombrecompletoelemento >' no contiene ningún miembro público o no se encuentra. Asegúrese de que el espacio de nombres o el tipo se define y contiene a al menos un miembro público. Asegúrese de que el nombre de alias no contiene otros alias.  
  
 Una propiedad de importación de un proyecto especifica un elemento contenedor que no se puede encontrar o no define `Public` miembros.  
  
 Un *que contiene el elemento* puede ser el espacio de nombres, clase, estructura, módulo, interfaz o enumeración. El elemento contenedor contiene a miembros, como variables, procedimientos u otros elementos que lo contiene.  
  
 El propósito de la importación es permitir que el código para obtener acceso a los miembros de tipo o espacio de nombres sin tener que calificarlos. También podría necesitar el proyecto agregar una referencia al espacio de nombres o tipo. Para obtener más información, vea "Importar elementos contenedores" en [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Si el compilador no encuentra el elemento contenedor especificado, no se puede resolver las referencias que lo usan. Si encuentra el elemento, pero el elemento no exponen ninguno `Public` miembros, ninguna referencia puede ser correcta. En cualquier caso, tiene sentido para importar el elemento.  
  
 Usa el **Diseñador de proyectos** para especificar los elementos que se van a importar. Use la **espacios de nombres importados** sección de la **referencias** página. Puede tener acceso a la **Diseñador de proyectos** haciendo doble clic en el **mi proyecto** icono en **el Explorador de soluciones**.  
  
 **Identificador de error:** BC40057  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Abra el **Diseñador de proyectos** y cambie a la **referencia** página.  
  
2. En el **espacios de nombres importados** sección, compruebe que el elemento contenedor es accesible desde el proyecto.  
  
3. Compruebe que el elemento contenedor expone al menos una `Public` miembro.  
  
## <a name="see-also"></a>Vea también

- [Página Referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
