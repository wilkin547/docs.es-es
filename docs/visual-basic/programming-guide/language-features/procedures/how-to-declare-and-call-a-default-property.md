---
title: Procedimiento Declarar y llamar a una propiedad predeterminada en Visual Basic
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
ms.openlocfilehash: ca282acbe6831f2189d83faa2f83d32d420d9b53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640971"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Procedimiento Declarar y llamar a una propiedad predeterminada en Visual Basic
Un *propiedad predeterminada* es una propiedad de clase o estructura que el código puede tener acceso sin especificarlo. Al llamar a los nombres de código de una clase o estructura, pero no una propiedad y el contexto permite el acceso a una propiedad, Visual Basic resuelve el acceso a esa clase o propiedad de la estructura predeterminada si existe alguno.  
  
 Una clase o estructura puede tener como máximo una propiedad predeterminada. Sin embargo, puede sobrecargar una propiedad predeterminada y tiene más de una versión de éste.  
  
 Para obtener más información, consulte [predeterminado](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Para declarar una propiedad predeterminada  
  
1.  Declare la propiedad de la manera normal. No se especifica la `Shared` o `Private` palabra clave.  
  
2.  Incluir el `Default` palabra clave en la declaración de propiedad.  
  
3.  Especifique al menos un parámetro para la propiedad. No se puede definir una propiedad predeterminada que no tiene al menos un argumento.  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>Para llamar a una propiedad predeterminada  
  
1.  Declare una variable del tipo de clase o estructura contenedora.  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Utilice el nombre de variable solo en una expresión donde normalmente incluiría el nombre de propiedad.  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  Siga el nombre de variable con una lista de argumentos entre paréntesis. Una propiedad predeterminada debe tener al menos un argumento.  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Para recuperar el valor de propiedad predeterminado, use el nombre de variable con una lista de argumentos en una expresión o siguiendo la igual (`=`) inicie sesión en una instrucción de asignación.  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Para establecer el valor de propiedad predeterminado, use el nombre de variable con una lista de argumentos, en el lado izquierdo de una instrucción de asignación.  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  Siempre puede especificar el nombre de propiedad predeterminado junto con el nombre de variable, justo como lo haría para tener acceso a cualquier otra propiedad.  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente declara una propiedad predeterminada en una clase.  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo llamar a la propiedad predeterminada `myProperty` en la clase `class1`. Las tres instrucciones de asignación almacenan valores en `myProperty`y el <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada lee los valores.  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 El uso más común de una propiedad predeterminada es la <xref:Microsoft.VisualBasic.Collection.Item%2A> propiedad en diversas clases de colección.  
  
## <a name="robust-programming"></a>Programación sólida  
 Propiedades predeterminadas pueden producir una pequeña reducción en caracteres de código fuente, pero puede hacer que su código más difícil de leer. Si el código de llamada no está familiarizado con la clase o estructura, cuando realiza una referencia al nombre de clase o estructura no puede estar seguro si esa referencia tiene acceso a la clase o estructura en Sí o una propiedad predeterminada. Esto puede conducir a errores del compilador o errores sutiles tiempo de ejecución de lógica.  
  
 Algo puede reducir la posibilidad de errores de propiedad predeterminado al usar siempre el [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer el tipo de compilador para la comprobación `On`.  
  
 Si va a usar una clase o estructura en el código, debe determinar si tiene una propiedad predeterminada y si es así, lo que su nombre es.  
  
 Debido a estos inconvenientes, considere la posibilidad de no definir propiedades predeterminadas. Para mejorar la legibilidad de código, debe también tener en cuenta siempre referencia explícitamente a todas las propiedades, propiedades incluso predeterminadas.  
  
## <a name="see-also"></a>Vea también
- [Procedimientos de propiedades](./property-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Predetermiado](../../../../visual-basic/language-reference/modifiers/default.md)
- [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)
- [Cómo: Crear una propiedad](./how-to-create-a-property.md)
- [Cómo: Declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Cómo: Llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)
- [Cómo: Establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)
- [Cómo: Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
