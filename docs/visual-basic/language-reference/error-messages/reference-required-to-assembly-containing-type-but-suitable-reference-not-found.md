---
title: Es necesaria una referencia al ensamblado '<assemblyidentity>' que contenga el tipo '<typename>', pero no se encontró una referencia adecuada debido a la ambigüedad entre los proyectos '<projectname1>' y '<projectname2>'
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: ca574bfe926b7b9df272e296190b36f8635263db
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162315"
---
# <a name="bc30969-reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a>BC30969: referencia necesaria para el ensamblado ' \<assemblyidentity> ' que contiene el tipo ' \<typename> ', pero no se pudo encontrar una referencia adecuada debido a la ambigüedad entre los proyectos ' \<projectname1> ' y ' \<projectname2> '

Una expresión usa un tipo como, por ejemplo, una clase, estructura, interfaz, enumeración o delegado, que se define fuera del proyecto. Sin embargo, hay referencias de proyectos a más de un ensamblado que definen ese tipo.

 Los proyectos citados generan ensamblados con el mismo nombre. Por lo tanto, el compilador no puede determinar qué ensamblado debe usar para el tipo al que se está accediendo.

 Para tener acceso a un tipo definido en otro ensamblado, el compilador Visual Basic debe tener una referencia a ese ensamblado. Debe ser una referencia única y no ambigua, que no produzca referencias circulares entre proyectos.

 **Identificador de error:** BC30969

## <a name="to-correct-this-error"></a>Para corregir este error

1. Determine qué proyecto produce el mejor ensamblado para que el proyecto haga referencia a este. Para tomar esta decisión, puede usar criterios como la facilidad de acceso a archivos y la frecuencia de las actualizaciones.

2. En las propiedades del proyecto, agregue una referencia al archivo que contiene el ensamblado que define el tipo que está utilizando.

## <a name="see-also"></a>Vea también

- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Solucionar problemas de referencias rotas](/visualstudio/ide/troubleshooting-broken-references)
