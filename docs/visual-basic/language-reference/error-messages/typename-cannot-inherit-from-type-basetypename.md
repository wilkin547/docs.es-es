---
title: '&#39;&lt;TypeName&gt; &#39; no puede heredar de &lt;tipo&gt; &#39; &lt;nombreDeTipoBase&gt; &#39; porque amplía el acceso de la base de &lt;tipo&gt; fuera del ensamblado'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: f747b2b24f5fecc22b9e1fbc6ba26b634e9ead2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598429"
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;TypeName&gt; &#39; no puede heredar de &lt;tipo&gt; &#39; &lt;nombreDeTipoBase&gt; &#39; porque amplía el acceso de la base de &lt;tipo&gt; fuera del ensamblado
Una clase o interfaz hereda de una clase base o interfaz, pero tiene un nivel de acceso menos restrictivo.  
  
 Por ejemplo, un `Public` interfaz hereda de un `Friend` interfaz, o un `Protected` clase hereda de una `Private` clase. Esto expone la clase base o interfaz para tener acceso a más allá del nivel deseado.  
  
 **Id. de error:** BC30910  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar el nivel de acceso de la clase o interfaz derivada para que sea al menos tan restrictiva como la de la clase base o interfaz.  
  
     -o bien-  
  
-   Si necesita el nivel de acceso menos restrictivo, quite el `Inherits` instrucción. No se puede heredar de una interfaz o clase base más restringido.  
  
## <a name="see-also"></a>Vea también  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
