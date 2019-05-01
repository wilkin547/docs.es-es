---
title: Es necesaria una referencia al ensamblado '<assemblyidentity>' que contenga el tipo '<typename>', pero no se encontró una referencia adecuada debido a la ambigüedad entre los proyectos '<projectname1>' y '<projectname2>'
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 9868598b32ae17ef5bfb5dd738f8a7541515f5ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013756"
---
# <a name="reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a>Necesaria una referencia al ensamblado '\<assemblyidentity >' que contiene el tipo '\<typename >', pero no se encontró una referencia adecuada debido a la ambigüedad entre los proyectos\<projectname1 >' y '\< projectname2 >'
Una expresión usa un tipo como, por ejemplo, una clase, estructura, interfaz, enumeración o delegado, que se define fuera del proyecto. Sin embargo, hay referencias de proyectos a más de un ensamblado que definen ese tipo.  
  
 Los proyectos citados generan ensamblados con el mismo nombre. Por lo tanto, el compilador no puede determinar qué ensamblado debe usar para el tipo al que se está accediendo.  
  
 Para obtener acceso a un tipo definido en otro ensamblado, el compilador de Visual Basic debe tener una referencia a ese ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.  
  
 **Identificador de error:** BC30969  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.  
  
2. En las propiedades del proyecto, agregue una referencia al archivo que contiene el ensamblado que define el tipo que está usando.  
  
## <a name="see-also"></a>Vea también

- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
