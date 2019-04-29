---
title: "'<typename>' no puede heredar del <type> '<basetypename>' porque amplía el acceso del <type> fuera del ensamblado"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: dc979a66c73fdf15a4349a003680156e0ce27ed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764366"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a>'\<typename >' no puede heredar de \<tipo > '\<nombreDeTipoBase >' porque expande el acceso de la base de \<tipo > fuera del ensamblado
Una clase o interfaz hereda de una clase base o interfaz, pero tiene un nivel de acceso menos restrictivo.  
  
 Por ejemplo, un `Public` interfaz hereda de un `Friend` interfaz, o un `Protected` clase hereda de un `Private` clase. Esto expone la clase base o interfaz para tener acceso a más allá del nivel deseado.  
  
 **Identificador de error:** BC30910  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Cambiar el nivel de acceso de la clase derivada o interfaz sea al menos tan restrictiva como de la clase base o interfaz.  
  
     -o bien-  
  
- Si necesita el nivel de acceso menos restrictivo, quite el `Inherits` instrucción. No se puede heredar de una clase base más restringido o interfaz.  
  
## <a name="see-also"></a>Vea también

- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
