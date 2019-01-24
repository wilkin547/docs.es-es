---
title: Diferencias entre sombrear y reemplazar (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: d60d668c97019418b30b89147e86f7beea1c31f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640694"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Diferencias entre sombrear y reemplazar (Visual Basic)
Al definir una clase que hereda de una clase base, a veces desea definir uno o más de los elementos de la clase base en la clase derivada. Sombrear y reemplazar ambos están disponibles para este propósito.  
  
## <a name="comparison"></a>Comparación  
 Sombrear y reemplazar se usan cuando una clase derivada hereda de una clase base, y ambos vuelven a definir un elemento declarado con otro. Sin embargo, hay diferencias significativas entre los dos.  
  
 La siguiente tabla compara sombrear y reemplazar.  
  
||||  
|---|---|---|  
|Punto de comparación|Sombrear|Reemplazar|  
|Propósito|Protege frente a una modificación posterior de clase base que introduce a un miembro que ya ha definido en la clase derivada|Consigue polimorfismo mediante la definición de una implementación diferente de un procedimiento o propiedad con la misma secuencia de llamada<sup>1</sup>|  
|Elemento redefinido|Cualquier tipo de elemento declarado|Solo un procedimiento (`Function`, `Sub`, o `Operator`) o una propiedad|  
|Redefinición de elemento|Cualquier tipo de elemento declarado|Solo un procedimiento o propiedad con la secuencia de llamada idéntica<sup>1</sup>|  
|Nivel de acceso de elemento de redefinición|Cualquier nivel de acceso|No se puede cambiar el nivel de acceso de elemento invalidado|  
|Lectura y escritura de elemento de redefinición|Cualquier combinación|No se puede cambiar la legibilidad o escritura de propiedad reemplazada|  
|Control sobre redefinición|Elemento de la clase base no puede cumplir o prohibir el sombreado|Puede especificar el elemento de la clase base `MustOverride`, `NotOverridable`, o `Overridable`|  
|Uso de la palabra clave|`Shadows` se recomienda en una clase derivada; `Shadows` supone si ninguna de ellas `Shadows` ni `Overrides` especificado<sup>2</sup>|`Overridable` o `MustOverride` necesarios en la clase base; `Overrides` necesarios en una clase derivada|  
|Herencia de elemento de redefinición por clases derivadas de la clase derivada|Sombrear elemento heredada por clases derivadas posteriores, elemento sombreado permanecen oculto<sup>3</sup>|Reemplazar elemento heredado por clases derivadas posteriores, elemento invalidado que todavía se reemplaza|  
  
 <sup>1</sup> el *secuencia de llamada* consta del tipo de elemento (`Function`, `Sub`, `Operator`, o `Property`), nombre, la lista de parámetros y tipo de valor devuelto. No se puede reemplazar un procedimiento con una propiedad o al revés. No se puede reemplazar un tipo de procedimiento (`Function`, `Sub`, o `Operator`) con otro tipo.  
  
 <sup>2</sup> si no se especifica `Shadows` o `Overrides`, el compilador emite un mensaje de advertencia que le ayudarán a estar seguro de qué tipo de redefinición que desea usar. Si omite la advertencia, se utiliza el mecanismo de sombreado.  
  
 <sup>3</sup> si el elemento reemplazado es inaccesible en una clase derivada posterior, no se hereda el sombreado. Por ejemplo, si se declara el elemento reemplazado como `Private`, una clase que deriva de la clase derivada hereda el elemento original en lugar del elemento reemplazado.  
  
## <a name="guidelines"></a>Instrucciones  
 Normalmente, usa a reemplazar en los casos siguientes:  
  
-   Define las clases derivadas polimórficas.  
  
-   Desea que la seguridad de que el compilador aplicar el tipo de elemento idéntico y la secuencia de llamada.  
  
 Normalmente, usa el sombreado en los casos siguientes:  
  
-   Se prevé que la clase base podría modificarse y define un elemento con el mismo nombre que el suyo.  
  
-   Desea la libertad de cambiar el tipo de elemento o secuencia de llamada.  
  
## <a name="see-also"></a>Vea también
- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Cómo: Ocultar una Variable con el mismo nombre que su Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Cómo: Ocultar una Variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Cómo: Obtener acceso a una Variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
