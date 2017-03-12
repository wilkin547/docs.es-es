---
title: "Cu&#225;ndo se debe usar una enumeraci&#243;n (Visual Basic) | Microsoft Docs"
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
  - "enumeraciones [Visual Basic]"
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Cu&#225;ndo se debe usar una enumeraci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las enumeraciones ofrecen un modo fácil de trabajar con conjuntos de constantes relacionadas.  Una enumeración, o `Enum`, es un nombre simbólico para un conjunto de valores.  Las enumeraciones se tratan como tipos de datos, y puede utilizarlas para crear conjuntos de constantes y usarlas con variables y propiedades.  
  
## Cuándo se debe utilizar una enumeración  
 Cuando un procedimiento acepta un conjunto limitado de variables, considere el uso de una enumeración.  Las enumeraciones hacen que el código sea más claro y legible, especialmente cuando se utilizan nombres significativos.  
  
 Entre las ventajas de utilizar las enumeraciones se incluyen:  
  
-   Reducir los errores producidos por números transpuestos o mal escritos.  
  
-   Facilitar el cambio de valores en el futuro.  
  
-   Facilitar la lectura del código, lo que significa que habrá menos posibilidad de errores.  
  
-   Garantizar la compatibilidad futura.  Con enumeraciones, es menos probable que haya errores en el código si alguien cambia los valores correspondientes a los nombres de miembros en el futuro.  
  
## Nombres de enumeraciones  
 Utilice una convención de nomenclatura para los miembros de enumeraciones.  Cuando [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] encuentra un nombre de miembro de una enumeración, se puede producir una excepción si otras bibliotecas de tipos a las que se hace referencia contienen el mismo nombre.  Utilice un prefijo único que identifique los valores de su aplicación o componente.  
  
 Cuando se hace referencia a un miembro de una enumeración, es necesario calificarlo con el nombre de la enumeración o utilizar si no la instrucción `Imports`.  Para obtener más información, vea [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## Enumeraciones predefinidas  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona varias enumeraciones predefinidas, como `FirstDayOfWeek` y `MsgBoxResul`t, para facilitar el código.  Para obtener una lista de ellas, consulte [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## Vea también  
 [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Cómo: Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Cómo: Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Enum \(Instrucción\)](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)