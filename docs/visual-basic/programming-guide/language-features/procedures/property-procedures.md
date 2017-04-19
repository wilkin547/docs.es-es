---
title: Procedimientos de propiedad (Visual Basic) | Documentos de Microsoft
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
- Set statement, Property procedures
- Visual Basic code, procedures
- return values, Property procedures
- syntax, Property procedures
- procedures, property
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], custom
- property procedures
- Get statement, property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f21d4c7d9bd8f14bbe7284bc08399e7ba6b466c3
ms.lasthandoff: 03/13/2017

---
# <a name="property-procedures-visual-basic"></a>Procedimientos de propiedad (Visual Basic)
Un procedimiento de propiedad es una serie de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] las instrucciones que manipulan una propiedad personalizada en un módulo, clase o estructura. Procedimientos de propiedad son también conocido como *descriptores de acceso de propiedad*.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Proporciona los procedimientos de propiedad siguientes:  
  
-   Un `Get` procedimiento devuelve el valor de una propiedad. Se llama cuando se tiene acceso a la propiedad en una expresión.  
  
-   Un `Set` procedimiento establece una propiedad en un valor, incluida una referencia de objeto. Se llama cuando se asigna un valor a la propiedad.  
  
 Normalmente se definen los procedimientos de propiedad en pares, mediante la `Get` y `Set` instrucciones, pero puede definir cualquier procedimiento únicamente si la propiedad es de sólo lectura ([instrucción Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o de sólo escritura ([instrucción Set](../../../../visual-basic/language-reference/statements/set-statement.md)).  
  
 Puede omitir el `Get` y `Set` procedimiento cuando se usa una propiedad implementada automáticamente. Para obtener más información, consulte [Auto-Implemented Properties](./auto-implemented-properties.md).  
  
 Puede definir propiedades en las clases, estructuras y módulos. Las propiedades son `Public` de forma predeterminada, lo que significa que se puede llamar desde cualquier lugar en la aplicación que puede tener acceso al contenedor de propiedades.  
  
 Para obtener una comparación de propiedades y variables, consulte [diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 Una propiedad se define mediante un bloque de código delimitado por las [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` instrucción. Dentro de este bloque, cada procedimiento property aparece como un bloque interno delimitado por una instrucción de declaración (`Get` o `Set`) y la búsqueda de coincidencias `End` declaración.  
  
 La sintaxis para declarar una propiedad y sus procedimientos es la siguiente:  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 La `Modifiers` puede especificar el nivel de acceso e información acerca de la sobrecarga, invalidación, uso compartido y sombreado, así como si la propiedad es de sólo lectura o de sólo escritura. El `AccessLevel` en el `Get` o `Set` procedimiento puede ser cualquier nivel más restrictivo que el nivel de acceso especificado por la propiedad en Sí. Para obtener más información, consulte [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Tipo de datos  
 Tipo de datos de la propiedad y el nivel de acceso principal se definen en el `Property` instrucción y no en los procedimientos de propiedad. Una propiedad puede tener sólo un tipo de datos. Por ejemplo, no se puede definir una propiedad para almacenar un `Decimal` valor pero recuperar un `Double` valor.  
  
### <a name="access-level"></a>Nivel de acceso  
 Sin embargo, puede definir un nivel de acceso principal para una propiedad y restringir aún más el nivel de acceso en uno de sus procedimientos de propiedad. Por ejemplo, puede definir un `Public` propiedad y, a continuación, defina un `Private Set` procedimiento. El `Get` procedimiento permanece `Public`. Puede cambiar el nivel de acceso sólo en uno de los procedimientos de la propiedad y sea aún más restrictivo que el nivel de acceso principal. Para obtener más información, consulte [Cómo: declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md).  
  
## <a name="parameter-declaration"></a>Declaración de parámetros  
 Declara cada parámetro de la misma manera que lo hace para [procedimientos Sub](./sub-procedures.md), salvo que el mecanismo para pasar argumentos debe ser `ByVal`.  
  
 La sintaxis para cada parámetro en la lista de parámetros es como sigue:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración. La sintaxis para especificar un valor predeterminado es el siguiente:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Valor de propiedad  
 En un `Get` procedimiento, el valor devuelto se suministra a la expresión de llamada como valor de la propiedad.  
  
 En un `Set` procedimiento, el nuevo valor de propiedad se pasa al parámetro de la `Set` instrucción. Si se declara explícitamente un parámetro, se debe declarar con el mismo tipo de datos que la propiedad. Si no se declara un parámetro, el compilador utiliza el parámetro implícito `Value` para representar el nuevo valor que se asignará a la propiedad.  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Invocar un procedimiento de propiedad implícitamente haciendo referencia a la propiedad. Utilice el nombre de la propiedad del mismo modo que utilizaría el nombre de una variable, excepto en que debe proporcionar valores para todos los argumentos que no sean opcionales, y debe incluir la lista de argumentos entre paréntesis. Si no se proporcionan argumentos, se pueden omitir los paréntesis.  
  
 La sintaxis de una llamada implícita a un `Set` procedimiento es el siguiente:  
  
 `propertyname[(argumentlist)] = expression`  
  
 La sintaxis de una llamada implícita a un `Get` procedimiento es el siguiente:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Ejemplo de declaración y llamada  
 La propiedad siguiente almacena un nombre completo como dos nombres constitutivos, el nombre y el apellido. Cuando se lee el código de llamada `fullName`, el `Get` procedimiento combina los dos nombres constitutivos y devuelve el nombre completo. Cuando el código de llamada asigna un nuevo nombre completo, el `Set` procedimiento intenta dividir en dos nombres constitutivos. Si no encuentra un espacio, almacena como el nombre.  
  
 [!code-vb[VbVbcnProcedures Nº&8;](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 El ejemplo siguiente muestra las llamadas típicas a los procedimientos de propiedad de `fullName`.  
  
 [!code-vb[VbVbcnProcedures&#9;](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Function (procedimientos)](./function-procedures.md)   
 [Procedimientos de operadores](./operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md)   
 [Cómo: crear una propiedad](./how-to-create-a-property.md)   
 [Cómo: llamar a un procedimiento de propiedad](./how-to-call-a-property-procedure.md)   
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Cómo: establecer un valor en una propiedad](./how-to-put-a-value-in-a-property.md)   
 [Obtener un valor de una propiedad](./how-to-get-a-value-from-a-property.md)
