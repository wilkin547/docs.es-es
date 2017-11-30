---
title: Diferencias entre sombrear y reemplazar (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d67486d9c6af96d314abad7142ba86779d74f5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Diferencias entre sombrear y reemplazar (Visual Basic)
Cuando se define una clase que hereda de una clase base, a veces desea volver a definir uno o varios de los elementos de la clase base en la clase derivada. Sombrear y reemplazar están disponibles para este propósito.  
  
## <a name="comparison"></a>Comparación  
 Sombrear y reemplazar se usan cuando una clase derivada hereda de una clase base y ambos vuelven a definir un elemento declarado con otro. Pero hay diferencias significativas entre los dos.  
  
 En la siguiente tabla compara sombrear y reemplazar.  
  
||||  
|---|---|---|  
|Punto de comparación|Sombrear|Reemplazar|  
|Finalidad|Protege frente a una modificación posterior de clase base que introduce a un miembro que ya se ha definido en la clase derivada|Logra polimorfismo mediante la definición de una implementación diferente de un procedimiento o propiedad con la misma secuencia que realiza la llamada<sup>1</sup>|  
|Elemento redefinido|Cualquier tipo de elemento declarado|Sólo un procedimiento (`Function`, `Sub`, o `Operator`) o una propiedad|  
|Elemento de redefinición|Cualquier tipo de elemento declarado|Sólo un procedimiento o propiedad con la secuencia de llamada idéntica<sup>1</sup>|  
|Nivel de acceso de elemento de redefinición|Cualquier nivel de acceso|No se puede cambiar el nivel de acceso de elemento invalidado|  
|Lectura y escritura de elemento de redefinición|Cualquier combinación|No se puede cambiar de lectura o escritura de la propiedad reemplazada|  
|Control sobre redefinición|Elemento de la clase base no puede cumplir o prohibir el sombreado|Puede especificar el elemento de la clase base `MustOverride`, `NotOverridable`, o`Overridable`|  
|Uso de la palabra clave|`Shadows`se recomienda en una clase derivada; `Shadows` supone si ninguna de ellas `Shadows` ni `Overrides` especificada<sup>2</sup>|`Overridable`o `MustOverride` necesarios en la clase base; `Overrides` necesarios en una clase derivada|  
|Herencia de elemento de redefinición mediante clases derivadas de la clase derivada|Sombrear elemento heredada por clases derivadas posteriores, elemento sombreado permanecen oculto<sup>3</sup>|Reemplace el elemento heredado por clases derivadas posteriores, elemento invalidado que todavía se reemplaza|  
  
 <sup>1</sup> el *secuencia de llamada* está formada por el tipo de elemento (`Function`, `Sub`, `Operator`, o `Property`), nombre, lista de parámetros y tipo de valor devuelto. No se puede reemplazar un procedimiento con una propiedad o al revés. No se puede reemplazar un tipo de procedimiento (`Function`, `Sub`, o `Operator`) con otro tipo.  
  
 <sup>2</sup> si no se especifica cualquiera `Shadows` o `Overrides`, el compilador emite un mensaje de advertencia que le ayudarán a estar seguro de qué tipo de redefinición que desea utilizar. Si omite la advertencia, se utiliza el mecanismo de sombreado.  
  
 <sup>3</sup> si el elemento reemplazado es inaccesible en una clase derivada posterior, dicho sombreado no se hereda. Por ejemplo, si se declara el elemento reemplazado como `Private`, una clase que deriva de la clase derivada hereda el elemento original en lugar del elemento reemplazado.  
  
## <a name="guidelines"></a>Instrucciones  
 Normalmente, se utiliza reemplazar en los casos siguientes:  
  
-   Define las clases derivadas polimórficas.  
  
-   Desea que la seguridad de que el compilador aplicar el tipo de elemento idéntico y la secuencia de llamada.  
  
 Normalmente, se utiliza sombrear en los casos siguientes:  
  
-   Se prevé que la clase base podría modificarse y define un elemento con el mismo nombre que el suyo.  
  
-   Desea que la libertad de cambiar el tipo de elemento o secuencia de llamada.  
  
## <a name="see-also"></a>Vea también  
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Ocultar una variable con el mismo nombre que su variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [Ocultar una variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Obtener acceso a una variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
