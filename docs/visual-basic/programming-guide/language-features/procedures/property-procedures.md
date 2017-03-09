---
title: "Procedimientos de propiedad (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Instrucción Set, procedimientos de Property"
  - "código de Visual Basic, procedimientos"
  - "valores devueltos, procedimientos de Property"
  - "sintaxis, procedimientos de Property"
  - "procedimientos, propiedad"
  - "código de Visual Basic, propiedades"
  - "procedimientos, llamada"
  - "propiedades [Visual Basic], personalizadas"
  - "procedimientos de propiedades"
  - "Instrucción Get, procedimientos de Property"
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Procedimientos de propiedad (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un procedimiento de propiedad es una serie de instrucciones de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] que manipulan una propiedad personalizada en un módulo, clase o estructura.  Los procedimientos Property también se conocen como *descriptores de acceso de propiedades*.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona los procedimientos de propiedad siguientes:  
  
-   Un procedimiento `Get` devuelve el valor de una propiedad.  Se le llama al tener acceso a la propiedad en una expresión.  
  
-   Un procedimiento `Set` establece una propiedad en un valor, incluida una referencia a objeto.  Se le llama al asignar un valor a la propiedad.  
  
 Se suelen definir procedimientos de propiedad en pares, mediante las instrucciones `Get` y `Set`, pero también se puede definir uno de los procedimientos solamente si la propiedad es de sólo lectura \([Get \(Instrucción\)](../../../../visual-basic/language-reference/statements/get-statement.md)\) o de sólo escritura \([Set \(Instrucción\)](../../../../visual-basic/language-reference/statements/set-statement.md)\).  
  
 Puede omitir el procedimiento `Get` y `Set` al utilizar una propiedad autoimplementada.  Para obtener más información, vea [Propiedades autoimplementadas](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Las propiedades pueden definirse en clases, estructuras y módulos.  Las propiedades son `Public` de manera predeterminada, lo que significa que es posible llamarlas desde cualquier parte de la aplicación que tenga acceso al contenedor de propiedades.  
  
 Para consultar una comparación de propiedades y variables, vea [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## Sintaxis de la declaración  
 Una propiedad en sí se define como un bloque de código delimitado por las instrucciones [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md) y `End Property`.  Dentro de este bloque, cada procedimiento de propiedad aparece como un bloque interno incluido entre una instrucción de declaración \(`Get` o `Set`\) y la declaración `End` correspondiente.  
  
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
  
 Los `Modifiers` pueden especificar un nivel de acceso e información relativo a la sobrecarga, al reemplazo, uso compartido y sombreado, y si la propiedad es de sólo lectura o de sólo escritura.  `AccessLevel` en el procedimiento de `Get` o de `Set` puede ser cualquier nivel más restrictivo que el nivel de acceso especificado para la propiedad.  Para obtener más información, vea [Property \(Instrucción\)](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### Tipo de datos  
 El tipo de datos de una propiedad y el nivel de acceso principal están definidos en la instrucción `Property` y no en los procedimientos de propiedad.  Una propiedad puede tener sólo un tipo de datos.  Por ejemplo, no puede definirse una propiedad para que almacene un valor `Decimal` y que recupere un valor `Double`.  
  
### Nivel de acceso  
 Sin embargo, puede definir un nivel de acceso principal para una propiedad y restringir aún más el nivel de acceso en uno de sus procedimientos de propiedad.  Por ejemplo, puede definir una propiedad `Public` y, a continuación, definir un procedimiento `Private Set`.  El procedimiento `Get` sigue siendo `Public`.  Puede cambiar el nivel de acceso en sólo uno de los procedimientos de una propiedad y que sea aún más restrictivo que el nivel de acceso principal.  Para obtener más información, vea [Cómo: Declarar una propiedad con niveles de acceso mixtos](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md).  
  
## Declaración de parámetros  
 Los parámetros se declaran de la misma manera que se declara [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md), excepto que el mecanismo para pasar argumentos debe ser `ByVal`.  
  
 La sintaxis de los parámetros de una lista de parámetros es la siguiente:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Si el parámetro es opcional, debe proporcionar también un valor predeterminado como parte de su declaración.  La sintaxis para especificar un valor predeterminado es la siguiente:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## Valor de propiedad  
 En un procedimiento `Get`, el valor devuelto se suministra a la expresión de llamada como valor de la propiedad.  
  
 En un procedimiento `Set`, el nuevo valor de propiedad se pasa al parámetro de la instrucción `Set`.  Si un parámetro se declara de forma explícita, el tipo de datos de éste debe ser el mismo que el de la propiedad.  Si no se declara un parámetro, el compilador utiliza el parámetro implícito `Value` para representar el nuevo valor que se va a asignar a la propiedad.  
  
## Sintaxis de llamada  
 Se invoca un procedimiento de propiedad implícitamente haciendo referencia a la propiedad.  Se utiliza el nombre de la propiedad del mismo modo que si se tratase del nombre de una variable, a excepción de que se deben suministrar valores para todos los argumentos que no sean opcionales e incluir la lista de argumentos entre paréntesis.  Si no se proporcionan argumentos, se puede omitir el paréntesis.  
  
 La sintaxis de una llamada implícita a un procedimiento `Set` es la siguiente:  
  
 `propertyname[(argumentlist)] = expression`  
  
 La sintaxis de una llamada implícita a un procedimiento `Get` es la siguiente:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### Ejemplo de declaración y llamada  
 La propiedad siguiente almacena un nombre completo como dos nombres constitutivos, el nombre y el apellido.  Cuando el código de llamada lee  `fullName`, el procedimiento `Get` combina los dos nombres constitutivos y devuelve el nombre completo.  Cuando el código de llamada asigna un nuevo nombre completo, el procedimiento `Set` intenta dividirlo en dos nombres constitutivos.  Si no encuentra espacio, lo almacena como nombre.  
  
 [!code-vb[VbVbcnProcedures#8](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/property-procedures_1.vb)]  
  
 El ejemplo siguiente muestra las llamadas típicas a los procedimientos de propiedad de `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/property-procedures_2.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Diferencias entre propiedades y variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Cómo: Crear una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [Cómo: Llamar a un procedimiento de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [Cómo: Establecer un valor en una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [Cómo: Obtener un valor de una propiedad](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)