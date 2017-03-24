---
title: "Namespace o el tipo especificado en las importaciones de nivel de proyecto&lt;qualifiedelementname&gt;&quot; no contienen ningún miembro público o no se puede encontrar | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
dev_langs:
- VB
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 5dae6f92f573a57d0974c860500bc7420f55a94f
ms.lasthandoff: 03/13/2017

---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace o el tipo especificado en las importaciones de nivel de proyecto&lt;qualifiedelementname&gt;' no contienen ningún miembro público o no se encuentra
Namespace o el tipo especificado en las importaciones de nivel de proyecto\<qualifiedelementname >' no contienen ningún miembro público o no se encuentra. Asegúrese de que el espacio de nombres o el tipo se define y contiene a al menos un miembro público. Asegúrese de que el nombre de alias no contiene otros alias.  
  
 Una propiedad de importación de un proyecto especifica un elemento contenedor que no se puede encontrar o no define cualquier `Public` miembros.  
  
 Un *que contiene el elemento* puede ser un espacio de nombres, clase, estructura, módulo, interfaz o enumeración. El elemento contenedor incluye a miembros, como variables, procedimientos u otros elementos que contienen.  
  
 El propósito de importar es permitir que el código para obtener acceso a miembros de tipo o espacio de nombres sin tener que calificarlos. El proyecto también necesite agregar una referencia al espacio de nombres o tipo. Para obtener más información, vea "Importar elementos contenedores" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Si el compilador no puede encontrar el elemento contenedor especificado, no puede resolver las referencias que lo usan. Si encuentra el elemento pero el elemento no expone `Public` miembros, ninguna referencia puede ser correcta. En cualquier caso, tiene sentido para importar el elemento.  
  
 Utiliza la **Project Designer** para especificar los elementos que se va a importar. Utilice la **espacios de nombres importados** sección de la **referencias** página. Puede tener acceso a la **Project Designer** haciendo doble clic en el **mi proyecto** icono en **el Explorador de soluciones**.  
  
 **Id. de error:** BC40057  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Abra la **Diseñador de proyectos** y cambie a la **referencia** página.  
  
2.  En el **espacios de nombres importados** sección, compruebe que el elemento contenedor es accesible desde su proyecto.  
  
3.  Compruebe que el elemento contenedor expone al menos una `Public` miembro.  
  
## <a name="see-also"></a>Vea también  
 [Página Referencias, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)   
 [NIB Cómo: modificar las propiedades de proyecto y opciones de configuración](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Público](../../../visual-basic/language-reference/modifiers/public.md)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
