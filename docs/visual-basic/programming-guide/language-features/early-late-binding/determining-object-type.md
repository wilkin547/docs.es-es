---
title: "Determinar tipos de objeto (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases [Visual Basic], descubrir a qué pertenece un objeto"
  - "variables de objeto, probar valores"
  - "objetos [Visual Basic], determinación de tipo"
  - "TypeName (función)"
  - "TypeOf...Is (expresión), tipo de objeto en tiempo de ejecución"
  - "tipos [Visual Basic], determinar tipos de objeto en Visual Basic"
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Determinar tipos de objeto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Las variables de objeto genéricas \(es decir, variables declaradas como `Object`\) pueden contener objetos de cualquier clase.  Al usar variables de tipo `Object`, puede ser necesario tomar medidas diferentes en función de la clase del objeto; por ejemplo, algunos objetos podrían no admitir una determinada propiedad o método.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona dos maneras de determinar qué tipo de objeto está almacenado en una variable de objeto: la función `TypeName` y el operador `TypeOf...Is`.  
  
## TypeName y TypeOf…Is  
 La función `TypeName` devuelve una cadena y es la opción más conveniente si se necesita almacenar o presentar el nombre de clase de un objeto, como se muestra en el fragmento de código siguiente:  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 El operador `TypeOf...Is` es idóneo para comprobar el tipo de un objeto, puesto que es mucho más rápido que una comparación de cadenas equivalente que utiliza `TypeName`.  El fragmento de código siguiente usa `TypeOf...Is` dentro de una instrucción `If...Then...Else`:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 Use este método con precaución.  El operador `TypeOf...Is` devuelve `True` si un objeto es de un tipo específico o si se deriva de un tipo específico.  Casi todas las tareas que se pueden realizar con [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] implican el uso de objetos, entre ellos algunos elementos que normalmente no se suponen objetos, por ejemplo, cadenas y enteros.  Estos objetos se derivan de <xref:System.Object> y heredan métodos de ellos.  Cuando se pasa un `Integer` y se evalúa con `Object`, el operador `TypeOf...Is` devuelve `True`.  El resultado del ejemplo siguiente declara que el parámetro `InParam` es a la vez `Object` e `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 En el ejemplo siguiente se utilizan `TypeOf...Is` y `TypeName` para determinar el tipo del objeto que se les pasa en el argumento `Ctrl`.  El procedimiento `TestObject` llama a `ShowType` con tres clases de controles diferentes.  
  
#### Para ejecutar el ejemplo  
  
1.  Cree un nuevo proyecto de aplicación para Windows y agregue al formulario un control <xref:System.Windows.Forms.Button>, un control <xref:System.Windows.Forms.CheckBox> y un control <xref:System.Windows.Forms.RadioButton>.  
  
2.  Llame al procedimiento `TestObject` desde el botón del formulario.  
  
3.  Agregue el código siguiente al formulario:  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>   
 [Llamar a una propiedad o método mediante un nombre de cadena](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)   
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [If...Then...Else \(Instrucción\)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [String \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Integer \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/integer-data-type.md)