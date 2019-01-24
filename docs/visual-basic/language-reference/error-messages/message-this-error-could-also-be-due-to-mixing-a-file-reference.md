---
title: '&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &#39; &lt;assemblyname&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: d4fb2a8985a21ecea5056b83d2766e8dc468180d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528997"
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a>&lt;mensaje&gt; este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado &#39; &lt;assemblyname&gt;&#39;
\<mensaje > Este error también podría ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado '\<assemblyname >. En este caso, intente reemplazar la referencia de archivo a '\<nombredearchivodeensamblado >' en el proyecto '\<projectname1 >' con una referencia de proyecto a '\<projectname2 >'.  
  
 Código del proyecto accede a un miembro de otro proyecto, pero la configuración de la solución no admite el compilador de Visual Basic resolver la referencia.  
  
 Para obtener acceso a un tipo definido en otro ensamblado, el compilador de Visual Basic debe tener una referencia a ese ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.  
  
 **Identificador de error:** BC30971  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.  
  
2.  En las propiedades del proyecto, agregue una referencia al proyecto que contiene el ensamblado que define el tipo que está usando.  
  
## <a name="see-also"></a>Vea también
- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
