---
title: "Namespace o el tipo especificado en las importaciones &#39; &lt;nombrecompletoelemento&gt;&#39; &#39; t contienen ningún miembro público o no se encuentra"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 49cd9fa5d5182b2cf2d7fc4623bc8e9aa02bf85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace o el tipo especificado en las importaciones &#39; &lt;nombrecompletoelemento&gt;&#39; &#39; t contienen ningún miembro público o no se encuentra
Namespace o el tipo especificado en las importaciones\<nombrecompletoelemento >' no contienen ningún miembro público o no se encuentra. Asegúrese de que el espacio de nombres o el tipo se define y contiene a al menos un miembro público. Asegúrese de que el nombre de alias no contiene otros alias.  
  
 Un `Imports` instrucción especifica un elemento contenedor que no se puede encontrar o no define `Public` miembros.  
  
 A *que contiene el elemento* puede ser un espacio de nombres, clase, estructura, módulo, interfaz o enumeración. El elemento contenedor incluye a miembros, como variables, procedimientos u otros elementos que lo contiene.  
  
 El propósito de la importación es permitir que el código para obtener acceso a los miembros de tipo o espacio de nombres sin tener que calificarlos. El proyecto también necesite agregar una referencia a un tipo o espacio de nombres. Para obtener más información, vea "Importar elementos contenedores" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Si el compilador no puede encontrar el elemento contenedor especificado, no se puede resolver las referencias que lo usan. Si encuentra el elemento pero el elemento no exponen ninguno `Public` miembros, ninguna referencia puede ser correcta. En cualquier caso, tiene sentido para importar el elemento.  
  
 Tenga en cuenta que si importa un elemento contenedor y asignarles un alias de importación, a continuación, no puede utilizar ese alias de importación para importar ningún otro elemento. El código siguiente genera un error del compilador.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **Id. de error:** BC40056  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe que el elemento contenedor es accesible desde el proyecto.  
  
2.  Compruebe que la especificación del elemento contenedor no incluye ningún alias de importación de importación en otro.  
  
3.  Compruebe que el elemento contenedor expone al menos una `Public` miembro.  
  
## <a name="see-also"></a>Vea también  
 [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Namespace (instrucción)](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
