---
title: "'<typename>' no puede heredar del <type> '<basetypename>' porque amplía el acceso del <type> fuera del ensamblado"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: aa04c558abbcc4259c2821cdcbdc1669b91ffee0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402777"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>'\<typename>' no puede heredar del \<type> '\<basetypename>' porque amplía el acceso del \<type> fuera del ensamblado
Una clase o interfaz hereda de una clase base o una interfaz, pero tiene un nivel de acceso menos restrictivo.  
  
 Por ejemplo, una `Public` interfaz hereda de una `Friend` interfaz o una `Protected` clase hereda de una `Private` clase. Esto expone la clase base o la interfaz para obtener acceso más allá del nivel previsto.  
  
 **Identificador de error:** BC30910  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Cambie el nivel de acceso de la clase o la interfaz derivada para que sea al menos tan restrictiva como la de la clase base o la interfaz.  
  
     O bien  
  
- Si necesita el nivel de acceso menos restrictivo, quite la `Inherits` instrucción. No se puede heredar de una interfaz o clase base más restringida.  
  
## <a name="see-also"></a>Consulte también

- [Instrucción Class](../statements/class-statement.md)
- [Instrucción Interface](../statements/interface-statement.md)
- [Inherits Statement](../statements/inherits-statement.md)
- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
