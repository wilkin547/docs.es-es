---
description: "Más información sobre: BC30961: el valor de tipo ' <typename1> ' no se puede convertir en ' <typename2> ' (varias referencias de archivo)"
title: Un valor de tipo '<typename1>' no se puede convertir a '<typename2>' (varias referencias de archivo)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 77f8f3c500f9f395d3998261a218175e49f0f52b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640867"
---
# <a name="bc30961-value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a>BC30961: el valor de tipo ' \<typename1> ' no se puede convertir en ' \<typename2> ' (varias referencias de archivo)

El valor de tipo ' \<typename1> ' no se puede convertir en ' \<typename2> '. La falta de coincidencia de tipos podría ser debido a la combinación de una referencia de archivo a ' \<filepath1> ' en el proyecto ' \<projectname1> ' con una referencia de archivo a ' \<filepath2> ' en el proyecto ' ' \<projectname2> . Si ambos ensamblados son idénticos, intente reemplazar estas referencias para que ambas procedan de la misma ubicación.

 En una situación en la que un proyecto realiza más de una referencia de archivo a un ensamblado, el compilador no puede garantizar que un tipo se pueda convertir en otro.

 Cada referencia de archivo especifica una ruta de acceso y un nombre de archivo para el archivo de salida de un proyecto (normalmente un archivo DLL). El compilador no puede garantizar que los archivos de salida proceden del mismo origen o que representan la misma versión del mismo ensamblado. Por lo tanto, no puede garantizar que los tipos de las distintas referencias son del mismo tipo, o incluso que se puede convertir en el otro.

 Puede usar una sola referencia de archivo si sabe que los ensamblados a los que se hace referencia tienen la misma identidad de ensamblado. La *identidad del ensamblado* incluye el nombre, la versión, la clave pública, si existe, y la referencia cultural del ensamblado. Esta información identifica de forma exclusiva el ensamblado.

 **Identificador de error:** BC30961

## <a name="to-correct-this-error"></a>Para corregir este error

- Si los ensamblados a los que se hace referencia tienen la misma identidad de ensamblado, quite o reemplace una de las referencias de archivo para que solo haya una referencia de archivo única.

- Si los ensamblados a los que se hace referencia no tienen la misma identidad de ensamblado, cambie el código para que no intente convertir un tipo de uno en un tipo en el otro.

## <a name="see-also"></a>Vea también

- [Conversiones de tipos en Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
