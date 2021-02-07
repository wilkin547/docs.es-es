---
description: 'Más información acerca de: Partial (Visual Basic)'
title: Parcial
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
ms.openlocfilehash: bf2d8b06b83f4a90ec2f4edd52405b58695c26e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701019"
---
# <a name="partial-visual-basic"></a>Partial (Visual Basic)

Indica que una declaración de tipo es una definición parcial del tipo.  
  
 Puede dividir la definición de un tipo en varias declaraciones con la palabra clave `Partial`. Puede usar todas las declaraciones parciales que quiera en todos los archivos de código fuente que desee, pero todas las declaraciones deben estar en el mismo ensamblado y en el mismo espacio de nombres.  
  
> [!NOTE]
> Visual Basic admite *métodos parciales*, que normalmente se implementan en clases parciales. Para obtener más información, vea [métodos parciales](../../programming-guide/language-features/procedures/partial-methods.md) y [Sub Statement](../statements/sub-statement.md).  
  
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
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`attrlist`|Opcional. Lista de atributos que se aplican a este tipo. Debe incluir la [lista de atributos](../statements/attribute-list.md) entre corchetes angulares ( `< >` ).|  
|`accessmodifier`|Opcional. Especifica qué código puede tener acceso a este tipo. Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Vea [Shadows](shadows.md).|  
|`MustInherit`|Opcional. Vea [MustInherit](mustinherit.md).|  
|`NotInheritable`|Opcional. Vea [NotInheritable](notinheritable.md).|  
|`name`|Necesario. Nombre de este tipo. Debe coincidir con el nombre definido en el resto de las declaraciones parciales del mismo tipo.|  
|`Of`|Opcional. Especifica que se trata de un tipo genérico. Vea [tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Obligatorio si se usa [de](../statements/of-clause.md). Consulte [lista de tipos](../statements/type-list.md).|  
|`Inherits`|Opcional. Vea [Inherits (instrucción](../statements/inherits-statement.md)).|  
|`classname`|Obligatorio si se usa `Inherits`. El nombre de la clase o la interfaz de la que se deriva esta clase.|  
|`Implements`|Opcional. Vea [Implements (instrucción](../statements/implements-statement.md)).|  
|`interfacenames`|Obligatorio si se usa `Implements`. Los nombres de las interfaces que implementa este tipo.|  
|`variabledeclarations`|Opcional. Instrucciones que declaran variables adicionales y eventos para el tipo.|  
|`proceduredeclarations`|Opcional. Instrucciones que declaran y definen procedimientos adicionales para el tipo.|  
|`End Class` o `End Structure`|Finaliza esta definición `Class` o `Structure` parcial.|  
  
## <a name="remarks"></a>Observaciones  

 Visual Basic usa definiciones de clase parcial para separar el código generado del código creado por el usuario en archivos de código fuente independientes. Por ejemplo, el **Diseñador de Windows Forms<xref:System.Windows.Forms.Form> define clases parciales para controles como**. No debe modificar el código generado en estos controles.  
  
 Todas las reglas para crear clases, estructuras, interfaces y módulos, como las reglas de uso y herencia de modificadores, se aplican al crear un tipo parcial.  
  
## <a name="best-practices"></a>Prácticas recomendadas  
  
- En circunstancias normales no debe dividir el desarrollo de un solo tipo en dos o más declaraciones. Por lo tanto, en la mayoría de los casos no necesita la palabra clave `Partial`.  
  
- Para mejorar la legibilidad, cada declaración parcial de un tipo debe incluir la palabra clave `Partial`. El compilador permite a lo sumo una declaración parcial para omitir la palabra clave; si hay dos o más que la omiten, el compilador señala un error.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Unión de declaraciones.** El compilador trata el tipo como la unión de todas sus declaraciones parciales. Todos los modificadores de todas las definiciones parciales se aplican a todo el tipo; además, todos los miembros de todas las definiciones parciales están disponibles para todo el tipo.  
  
- **Promoción de tipos no permitida para los tipos parciales en los módulos.** Si una definición parcial está dentro de un módulo, se rechaza automáticamente la promoción de tipos de ese tipo. En este caso, un conjunto de definiciones parciales puede producir resultados inesperados e incluso errores del compilador. Para obtener más información, consulte [promoción de tipos](../../programming-guide/language-features/declared-elements/type-promotion.md).  
  
     El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.  
  
 La palabra clave `Partial` se puede usar en los siguientes contextos:  
  
 [Instrucción Class](../statements/class-statement.md)  
  
 [Structure (Instrucción)](../statements/structure-statement.md)  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se divide la definición de la clase `sampleClass` en dos declaraciones, cada una de las cuales define otro procedimiento `Sub`.  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 Las dos definiciones parciales del ejemplo anterior podrían estar en el mismo archivo de origen o en dos archivos distintos.  
  
## <a name="see-also"></a>Vea también

- [Instrucción Class](../statements/class-statement.md)
- [Structure (Instrucción)](../statements/structure-statement.md)
- [Promoción de tipos](../../programming-guide/language-features/declared-elements/type-promotion.md)
- [Shadows](shadows.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Métodos Partial](../../programming-guide/language-features/procedures/partial-methods.md)
