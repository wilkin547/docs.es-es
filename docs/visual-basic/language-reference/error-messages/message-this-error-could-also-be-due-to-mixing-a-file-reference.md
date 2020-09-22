---
title: <message> Este error también puede ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado "<assemblyname>"
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: cd2c00bda5b63abbd6bf7069ef28d0a812b22044
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873781"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a>\<message> Este error también puede ser debido a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado "\<assemblyname>"

\<message> Este error también podría deberse a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado ' \<assemblyname> . En este caso, intente reemplazar la referencia de archivo a ' \<assemblyfilename> ' en el proyecto ' \<projectname1> ' con una referencia de proyecto a ' \<projectname2> '.  
  
 El código del proyecto accede a un miembro de otro proyecto, pero la configuración de la solución no permite que el compilador de Visual Basic resuelva la referencia.  
  
 Para tener acceso a un tipo definido en otro ensamblado, el compilador Visual Basic debe tener una referencia a ese ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.  
  
 **Identificador de error:** BC30971  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.  
  
2. En las propiedades del proyecto, agregue una referencia al proyecto que contiene el ensamblado que define el tipo que está usando.  
  
## <a name="see-also"></a>Consulte también

- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
