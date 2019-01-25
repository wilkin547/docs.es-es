---
title: '&#39;&lt;TypeName&gt; &#39; no puede heredar de &lt;tipo&gt; &#39; &lt;nombreDeTipoBase&gt; &#39; porque amplía el acceso de la base de &lt;tipo&gt; fuera del ensamblado'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 108025132bdd0fa86df5ed142aaa39c7b7e18062
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556488"
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;TypeName&gt; &#39; no puede heredar de &lt;tipo&gt; &#39; &lt;nombreDeTipoBase&gt; &#39; porque amplía el acceso de la base de &lt;tipo&gt; fuera del ensamblado
Una clase o interfaz hereda de una clase base o interfaz, pero tiene un nivel de acceso menos restrictivo.  
  
 Por ejemplo, un `Public` interfaz hereda de un `Friend` interfaz, o un `Protected` clase hereda de un `Private` clase. Esto expone la clase base o interfaz para tener acceso a más allá del nivel deseado.  
  
 **Identificador de error:** BC30910  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar el nivel de acceso de la clase derivada o interfaz sea al menos tan restrictiva como de la clase base o interfaz.  
  
     O bien  
  
-   Si necesita el nivel de acceso menos restrictivo, quite el `Inherits` instrucción. No se puede heredar de una clase base más restringido o interfaz.  
  
## <a name="see-also"></a>Vea también
- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
