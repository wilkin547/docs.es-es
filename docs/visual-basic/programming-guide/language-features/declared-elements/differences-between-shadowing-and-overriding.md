---
title: Diferencias entre sombrear y reemplazar
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: a6ea83fadf18ef3be778e6de31c0eb4e65e74824
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392875"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Diferencias entre sombrear y reemplazar (Visual Basic)
Cuando se define una clase que hereda de una clase base, a veces se desea volver a definir uno o varios de los elementos de la clase base de la clase derivada. La sombra y el reemplazo están disponibles para este fin.  
  
## <a name="comparison"></a>De comparación  
 Las sombras e invalidaciones se usan cuando una clase derivada hereda de una clase base y ambos vuelven a definir un elemento declarado con otro. Pero hay diferencias significativas entre los dos.  
  
 En la tabla siguiente se compara la sombra con la invalidación.  
  
||||  
|---|---|---|  
|Punto de comparación|Sombreado|Invalidación|  
|Propósito|Protege frente a una modificación posterior de la clase base que introduce un miembro que ya se ha definido en la clase derivada.|Consigue el polimorfismo definiendo una implementación diferente de un procedimiento o una propiedad con la misma secuencia de llamada<sup>1</sup> .|  
|Elemento redefinido|Cualquier tipo de elemento declarado|Solo un procedimiento ( `Function` , `Sub` o `Operator` ) o la propiedad|  
|Elemento redefine|Cualquier tipo de elemento declarado|Solo un procedimiento o una propiedad con la secuencia de llamada idéntica<sup>1</sup>|  
|Nivel de acceso de redefine el elemento|Cualquier nivel de acceso|No se puede cambiar el nivel de acceso de un elemento invalidado|  
|Legibilidad y escritura de elemento de redefinición|Cualquier combinación|No se puede cambiar la legibilidad ni la escritura de la propiedad invalidada|  
|Controlar la redefinición|El elemento de clase base no puede aplicar ni prohibir el sombreado|El elemento de clase base puede especificar `MustOverride` , `NotOverridable` o`Overridable`|  
|Uso de palabras clave|`Shadows`recomendado en la clase derivada; se presupone si no se ha `Shadows` especificado ninguno de los `Shadows` `Overrides` <sup>dos</sup>|`Overridable`o `MustOverride` obligatorio en la clase base; se `Overrides` requiere en la clase derivada|  
|Herencia del elemento de redefinición por clases que derivan de la clase derivada|Elemento de sombreado heredado por otras clases derivadas; elemento sombreado todavía oculto<sup>3</sup>|Reemplazar el elemento heredado por otras clases derivadas; el elemento reemplazado todavía se ha invalidado|  
  
 <sup>1</sup> la *secuencia de llamada* está formada por el tipo de elemento ( `Function` , `Sub` , `Operator` o `Property` ), el nombre, la lista de parámetros y el tipo de valor devuelto. No se puede invalidar un procedimiento con una propiedad o viceversa. No se puede reemplazar un tipo de procedimiento ( `Function` , `Sub` o `Operator` ) por otro tipo.  
  
 <sup>2</sup> si no especifica `Shadows` ni `Overrides` , el compilador emite un mensaje de advertencia para ayudarle a asegurarse de qué tipo de redefinición desea utilizar. Si omite la advertencia, se utiliza el mecanismo de sombreado.  
  
 <sup>3</sup> si no se puede obtener acceso al elemento de sombreado en una clase derivada adicional, no se hereda el sombreado. Por ejemplo, si declara el elemento de sombreado como `Private` , una clase que deriva de la clase derivada hereda el elemento original en lugar del elemento de sombreado.  
  
## <a name="guidelines"></a>Instrucciones  
 Normalmente se usa la invalidación en los casos siguientes:  
  
- Está definiendo clases derivadas polimórficas.  
  
- Desea la seguridad de que el compilador aplique el tipo de elemento idéntico y la secuencia de llamada.  
  
 Normalmente se usa el sombreado en los casos siguientes:  
  
- Prevé que la clase base podría modificarse y definir un elemento con el mismo nombre que el suyo.  
  
- Desea la libertad de cambiar el tipo de elemento o la secuencia de llamada.  
  
## <a name="see-also"></a>Consulte también

- [References to Declared Elements](references-to-declared-elements.md)
- [Sombrear en Visual Basic](shadowing.md)
- [Procedimiento para ocultar una variable con el mismo nombre que su variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedimiento para ocultar una variable heredada](how-to-hide-an-inherited-variable.md)
- [Procedimiento para obtener acceso a una variable que se encuentra oculta por una clase derivada](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [Invalidaciones](../../../language-reference/modifiers/overrides.md)
