---
description: "Más información sobre: BC30955: el valor de tipo ' <typename1> ' no se puede convertir en '<typename2>"
title: Un valor de tipo '<typename1>' no se puede convertir a '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: e03201d5dbb84faf06b7acbe42fe6b3bb4272ab9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666256"
---
# <a name="bc30955-value-of-type-typename1-cannot-be-converted-to-typename2"></a>BC30955: el valor de tipo ' \<typename1> ' no se puede convertir en ' \<typename2> '

El valor de tipo ' \<typename1> ' no se puede convertir en ' \<typename2> '. La falta de coincidencia de tipos podría deberse a la combinación de una referencia de archivo con una referencia de proyecto al ensamblado ' \<assemblyname> '. Intente reemplazar la referencia de archivo a ' \<filepath> ' en el proyecto ' \<projectname1> ' con una referencia de proyecto a ' \<projectname2> '.

 En una situación en la que un proyecto realiza una referencia de proyecto y una referencia de archivo, el compilador no puede garantizar que un tipo se pueda convertir en otro.

 En el siguiente pseudocódigo se muestra una situación que puede generar este error.

 `' ================ Visual Basic project P1 ================`

 `'        P1 makes a PROJECT REFERENCE to project P2`

 `'        and a FILE REFERENCE to project P3.`

 `Public commonObject As P3.commonClass`

 `commonObject = P2.getCommonClass()`

 `' ================ Visual Basic project P2 ================`

 `'        P2 makes a PROJECT REFERENCE to project P3`

 `Public Function getCommonClass() As P3.commonClass`

 `Return New P3.commonClass`

 `End Function`

 `' ================ Visual Basic project P3 ================`

 `Public Class commonClass`

 `End Class`

 Project `P1` realiza una referencia de proyecto indirecta a través de Project `P2` a Project `P3` y también una referencia de archivo directo a `P3` . La declaración de `commonObject` utiliza la referencia de archivo a `P3` , mientras que la llamada a `P2.getCommonClass` usa la referencia de proyecto a `P3` .

 El problema en esta situación es que la referencia de archivo especifica una ruta de acceso y un nombre de archivo para el archivo de salida de `P3` (normalmente p3.dll), mientras que las referencias del proyecto identifican el proyecto de origen ( `P3` ) por nombre de proyecto. Por este motivo, el compilador no puede garantizar que el tipo `P3.commonClass` proceda del mismo código fuente a través de las dos referencias diferentes.

 Esta situación suele producirse cuando se mezclan las referencias de proyecto y las referencias de archivo. En la ilustración anterior, el problema no se produce si se `P1` realiza una referencia de proyecto directa a en `P3` lugar de una referencia de archivo.

 **Identificador de error:** BC30955

## <a name="to-correct-this-error"></a>Para corregir este error

- Cambie la referencia de archivo a una referencia de proyecto.

## <a name="see-also"></a>Vea también

- [Conversiones de tipos en Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
