---
title: Procedimiento para declarar y llamar a una propiedad predeterminada
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 4de5d94a94e764d1fc543ffae41b00a9bb729c94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388159"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic
Una *propiedad predeterminada* es una propiedad de clase o estructura a la que el código puede tener acceso sin especificarla. Cuando el código de llamada llama a una clase o estructura, pero no a una propiedad, y el contexto permite el acceso a una propiedad, Visual Basic resuelve el acceso a la propiedad predeterminada de la clase o la estructura, si existe una.  
  
 Una clase o estructura puede tener como máximo una propiedad predeterminada. Sin embargo, puede sobrecargar una propiedad predeterminada y tener más de una versión.  
  
 Para obtener más información, vea [default](../../../language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Para declarar una propiedad predeterminada  
  
1. Declare la propiedad de la manera normal. No especifique la `Shared` `Private` palabra clave o.  
  
2. Incluya la `Default` palabra clave en la declaración de propiedad.  
  
3. Especifique al menos un parámetro para la propiedad. No se puede definir una propiedad predeterminada que no tome al menos un argumento.  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a>Para llamar a una propiedad predeterminada  
  
1. Declare una variable de la clase contenedora o el tipo de estructura.  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. Use el nombre de la variable solo en una expresión en la que normalmente incluiría el nombre de la propiedad.  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. Siga el nombre de la variable con una lista de argumentos entre paréntesis. Una propiedad predeterminada debe tomar al menos un argumento.  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. Para recuperar el valor de propiedad predeterminado, use el nombre de la variable, con una lista de argumentos, en una expresión o siguiendo el signo igual ( `=` ) en una instrucción de asignación.  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. Para establecer el valor predeterminado de la propiedad, use el nombre de la variable, con una lista de argumentos, en el lado izquierdo de una instrucción de asignación.  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. Siempre puede especificar el nombre de la propiedad predeterminada junto con el nombre de la variable, tal y como haría para tener acceso a cualquier otra propiedad.  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara una propiedad predeterminada en una clase.  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo llamar a la propiedad predeterminada `myProperty` en la clase `class1` . Las tres instrucciones de asignación almacenan valores en `myProperty` y la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada Lee los valores.  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 El uso más común de una propiedad predeterminada es la <xref:Microsoft.VisualBasic.Collection.Item%2A> propiedad de varias clases de colección.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las propiedades predeterminadas pueden dar lugar a una pequeña reducción en los caracteres de código fuente, pero pueden hacer que el código sea más difícil de leer. Si el código de llamada no está familiarizado con su clase o estructura, cuando hace referencia al nombre de la clase o de la estructura no puede estar seguro de si esa referencia tiene acceso a la clase o estructura, o a una propiedad predeterminada. Esto puede provocar errores del compilador o errores de lógica sutiles en tiempo de ejecución.  
  
 Puede reducir en cierta medida la posibilidad de que se produzcan errores de propiedad predeterminados Si usa siempre la [instrucción Option Strict](../../../language-reference/statements/option-strict-statement.md) para establecer la comprobación del tipo de compilador en `On` .  
  
 Si piensa utilizar una clase o estructura predefinida en el código, debe determinar si tiene una propiedad predeterminada y, en ese caso, cuál es su nombre.  
  
 Debido a estas desventajas, considere la posibilidad de no definir las propiedades predeterminadas. Para facilitar la lectura del código, también debe considerar la posibilidad de hacer referencia siempre a todas las propiedades explícitamente, incluso a las propiedades predeterminadas.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos de propiedad](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Valor predeterminado](../../../language-reference/modifiers/default.md)
- [Diferencias entre propiedades y variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Procedimiento para crear una propiedad](./how-to-create-a-property.md)
- [Procedimiento para declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedimiento para llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Procedimiento para establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Procedimiento para obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
