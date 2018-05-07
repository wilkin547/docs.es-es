---
title: Namespace o el tipo especificado en las importaciones de nivel de proyecto &#39; &lt;nombrecompletoelemento&gt; &#39; &#39;t contienen ningún miembro público o no se encuentra
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: d6d0c931262d892ec3e65888a76f25218b23d868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace o el tipo especificado en las importaciones de nivel de proyecto &#39; &lt;nombrecompletoelemento&gt; &#39; &#39;t contienen ningún miembro público o no se encuentra
Namespace o el tipo especificado en las importaciones de nivel de proyecto\<nombrecompletoelemento >' no contienen ningún miembro público o no se encuentra. Asegúrese de que el espacio de nombres o el tipo se define y contiene a al menos un miembro público. Asegúrese de que el nombre de alias no contiene otros alias.  
  
 Una propiedad de importación de un proyecto especifica un elemento contenedor que no se puede encontrar o no define `Public` miembros.  
  
 A *que contiene el elemento* puede ser un espacio de nombres, clase, estructura, módulo, interfaz o enumeración. El elemento contenedor incluye a miembros, como variables, procedimientos u otros elementos que lo contiene.  
  
 El propósito de la importación es permitir que el código para obtener acceso a los miembros de tipo o espacio de nombres sin tener que calificarlos. El proyecto también necesite agregar una referencia a un tipo o espacio de nombres. Para obtener más información, vea "Importar elementos contenedores" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Si el compilador no puede encontrar el elemento contenedor especificado, no se puede resolver las referencias que lo usan. Si encuentra el elemento pero el elemento no exponen ninguno `Public` miembros, ninguna referencia puede ser correcta. En cualquier caso, tiene sentido para importar el elemento.  
  
 Usa el **Diseñador de proyectos** para especificar los elementos que se va a importar. Use la **espacios de nombres importados** sección de la **referencias** página. Puede tener acceso a la **Diseñador de proyectos** haciendo doble clic en el **mi proyecto** icono en **el Explorador de soluciones**.  
  
 **Id. de error:** BC40057  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Abra la **Diseñador de proyectos** y cambie a la **referencia** página.  
  
2.  En el **espacios de nombres importados** sección, compruebe que el elemento contenedor es accesible desde el proyecto.  
  
3.  Compruebe que el elemento contenedor expone al menos una `Public` miembro.  
  
## <a name="see-also"></a>Vea también  
 [Página Referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
