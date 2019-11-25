---
title: Partial
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: df85571b757fd54496677bad1195fab9690b79cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351357"
---
# <a name="partial-visual-basic"></a>Partial (Visual Basic)
Indica que una declaración de tipo es una definición parcial del tipo.  
  
 Puede dividir la definición de un tipo en varias declaraciones con la palabra clave `Partial`. Puede usar todas las declaraciones parciales que quiera en todos los archivos de código fuente que desee, pero todas las declaraciones deben estar en el mismo ensamblado y en el mismo espacio de nombres.  
  
> [!NOTE]
> Visual Basic supports *partial methods*, which are typically implemented in partial classes. For more information, see [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|---|---|  
|`attrlist`|Opcional. Lista de atributos que se aplican a este tipo. You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets (`< >`).|  
|`accessmodifier`|Opcional. Especifica qué código puede tener acceso a este tipo. Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Opcional. See [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Opcional. See [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`name`|Requerido. Nombre de este tipo. Debe coincidir con el nombre definido en el resto de las declaraciones parciales del mismo tipo.|  
|`Of`|Opcional. Especifica que se trata de un tipo genérico. See [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Required if you use [Of](../../../visual-basic/language-reference/statements/of-clause.md). See [Type List](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional. See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Obligatorio si se usa `Inherits`. El nombre de la clase o la interfaz de la que se deriva esta clase.|  
|`Implements`|Opcional. See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Obligatorio si se usa `Implements`. Los nombres de las interfaces que implementa este tipo.|  
|`variabledeclarations`|Opcional. Instrucciones que declaran variables adicionales y eventos para el tipo.|  
|`proceduredeclarations`|Opcional. Instrucciones que declaran y definen procedimientos adicionales para el tipo.|  
|`End Class` o `End Structure`|Finaliza esta definición `Class` o `Structure` parcial.|  
  
## <a name="remarks"></a>Comentarios  
 Visual Basic usa definiciones de clase parcial para separar el código generado del código creado por el usuario en archivos de código fuente independientes. Por ejemplo, el **Diseñador de Windows Forms<xref:System.Windows.Forms.Form> define clases parciales para controles como** . No debe modificar el código generado en estos controles.  
  
 Todas las reglas para crear clases, estructuras, interfaces y módulos, como las reglas de uso y herencia de modificadores, se aplican al crear un tipo parcial.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
  
- En circunstancias normales no debe dividir el desarrollo de un solo tipo en dos o más declaraciones. Por lo tanto, en la mayoría de los casos no necesita la palabra clave `Partial`.  
  
- Para mejorar la legibilidad, cada declaración parcial de un tipo debe incluir la palabra clave `Partial`. El compilador permite a lo sumo una declaración parcial para omitir la palabra clave; si hay dos o más que la omiten, el compilador señala un error.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Union of Declarations.** El compilador trata el tipo como la unión de todas sus declaraciones parciales. Todos los modificadores de todas las definiciones parciales se aplican a todo el tipo; además, todos los miembros de todas las definiciones parciales están disponibles para todo el tipo.  
  
- **Type Promotion Not Allowed For Partial Types in Modules.** Si una definición parcial está dentro de un módulo, se rechaza automáticamente la promoción de tipos de ese tipo. En este caso, un conjunto de definiciones parciales puede producir resultados inesperados e incluso errores del compilador. For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
     El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.  
  
 La palabra clave `Partial` se puede usar en los siguientes contextos:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se divide la definición de la clase `sampleClass` en dos declaraciones, cada una de las cuales define otro procedimiento `Sub`.  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 Las dos definiciones parciales del ejemplo anterior podrían estar en el mismo archivo de origen o en dos archivos distintos.  
  
## <a name="see-also"></a>Vea también

- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Métodos Partial](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
