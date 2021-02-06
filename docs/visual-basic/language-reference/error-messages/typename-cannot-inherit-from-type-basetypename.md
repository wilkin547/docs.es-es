---
description: "Más información sobre: BC30910: ' <typename> ' no puede heredar de <type> ' <basetypename> ' porque expande el acceso de la base <type> fuera del ensamblado"
title: "'<typename>' no puede heredar del <type> '<basetypename>' porque amplía el acceso del <type> fuera del ensamblado"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 332bfcbe9345f03605d6e1d6ded4a3e931ed491f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641101"
---
# <a name="bc30910-typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>BC30910: ' \<typename> ' no puede heredar de \<type> ' \<basetypename> ' porque expande el acceso de la base \<type> fuera del ensamblado

Una clase o interfaz hereda de una clase base o una interfaz, pero tiene un nivel de acceso menos restrictivo.

 Por ejemplo, una `Public` interfaz hereda de una `Friend` interfaz o una `Protected` clase hereda de una `Private` clase. Esto expone la clase base o la interfaz para obtener acceso más allá del nivel previsto.

 **Identificador de error:** BC30910

## <a name="to-correct-this-error"></a>Para corregir este error

- Cambie el nivel de acceso de la clase o la interfaz derivada para que sea al menos tan restrictiva como la de la clase base o la interfaz.

     o bien

- Si necesita el nivel de acceso menos restrictivo, quite la `Inherits` instrucción. No se puede heredar de una interfaz o clase base más restringida.

## <a name="see-also"></a>Vea también

- [Instrucción Class](../statements/class-statement.md)
- [Instrucción Interface](../statements/interface-statement.md)
- [Inherits Statement](../statements/inherits-statement.md)
- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
