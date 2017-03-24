---
title: "Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ce98e7fe72a395f6c4cde481feaa60be28c6fcc3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic
Un *propiedad predeterminada* es una propiedad de clase o estructura que el código puede tener acceso sin especificarlo. Al llamar a código nombres una clase o estructura pero no una propiedad, y el contexto permite tener acceso a una propiedad [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resuelve el acceso a esa clase o propiedad de la estructura predeterminada, si existe.  
  
 Una clase o estructura puede tener a lo sumo una propiedad predeterminada. Sin embargo, puede sobrecargar una propiedad predeterminada y tener más de una versión del mismo.  
  
 Para obtener más información, consulte [predeterminado](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Para declarar una propiedad predeterminada  
  
1.  Declare la propiedad de la manera normal. No se especifica la `Shared` o `Private` (palabra clave).  
  
2.  Incluir el `Default` palabra clave en la declaración de propiedad.  
  
3.  Especifique al menos un parámetro de la propiedad. No se puede definir una propiedad predeterminada que no tiene al menos un argumento.  
  
     [!code-vb[VbVbcnProcedures&#17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>Para llamar a una propiedad predeterminada  
  
1.  Declare una variable del tipo de clase o estructura contenedora.  
  
     [!code-vb[VbVbcnProcedures Nº&16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Utilice el nombre de variable solo en una expresión donde normalmente incluiría el nombre de propiedad.  
  
     [!code-vb[21 VbVbcnProcedures](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  Siga el nombre de variable con una lista de argumentos entre paréntesis. Una propiedad predeterminada debe tener al menos un argumento.  
  
     [!code-vb[VbVbcnProcedures&#20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Para recuperar el valor de propiedad predeterminado, utilice el nombre de variable con una lista de argumentos en una expresión o tras la igual (`=`) inicie sesión en una instrucción de asignación.  
  
     [!code-vb[VbVbcnProcedures&#15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Para establecer el valor de propiedad predeterminado, utilice el nombre de variable con una lista de argumentos, en el lado izquierdo de una instrucción de asignación.  
  
     [!code-vb[VbVbcnProcedures&#14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  Siempre puede especificar el nombre de propiedad predeterminado junto con el nombre de variable como haría para tener acceso a cualquier otra propiedad.  
  
     [!code-vb[VbVbcnProcedures Nº&19;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara una propiedad predeterminada en una clase.  
  
 [!code-vb[VbVbcnProcedures&#12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo llamar a la propiedad predeterminada `myProperty` en la clase `class1`. Las tres instrucciones de asignación almacenan valores en `myProperty`y el <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>llamada lee los valores.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
 [!code-vb[VbVbcnProcedures&#13;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 El uso más común de una propiedad predeterminada es la <xref:Microsoft.VisualBasic.Collection.Item%2A>propiedad en diversas clases de colección.</xref:Microsoft.VisualBasic.Collection.Item%2A>  
  
## <a name="robust-programming"></a>Programación sólida  
 Propiedades predeterminadas pueden producir una pequeña reducción en caracteres de código fuente, pero puede hacer el código más difícil de leer. Si el código de llamada no está familiarizado con su clase o estructura, cuando hace referencia al nombre de clase o estructura no puede ser determinado si accede a que hacen referencia a la clase o estructura en Sí o una propiedad predeterminada. Esto puede conducir a errores del compilador o errores sutiles lógica en tiempo de ejecución.  
  
 Puede reducir levemente la posibilidad de errores de la propiedad de forma predeterminada al usar siempre el [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer el tipo de compilador de comprobación `On`.  
  
 Si planea usar una clase o estructura en el código, debe determinar si posee una propiedad predeterminada y si es así, lo que su nombre es.  
  
 Debido a estas desventajas, considere la posibilidad de no definir propiedades predeterminadas. Para la legibilidad del código, debe tener en cuenta siempre referencia explícitamente a todas las propiedades, incluso predeterminados propiedades.  
  
## <a name="see-also"></a>Vea también  
 [Property (procedimientos)](./property-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Valor predeterminado](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)   
 [Cómo: crear una propiedad](./how-to-create-a-property.md)   
 [Cómo: declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Cómo: llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)   
 [Cómo: establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)   
 [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
