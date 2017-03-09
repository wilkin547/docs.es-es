---
title: "Tipos de valor y tipos de referencia | Microsoft Docs"
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
  - "tipos de datos [Visual Basic], tipos de referencia"
  - "tipos de datos [Visual Basic], tipos de valor"
  - "tipos de datos de referencia"
  - "tipos de referencia"
  - "tipos [Visual Basic]"
  - "tipos de datos de valor"
  - "tipos de valor"
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Tipos de valor y tipos de referencia
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En Visual Basic, los tipos de datos se implementan basado en su clasificación.  Los tipos de datos de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] se pueden clasificar en función de si una variable de un tipo específico almacena sus propios datos o un puntero a los datos.  Si almacena sus propios datos, se trata de un *tipo de valor*; si contiene un puntero a los datos guardados en cualquier otro lugar de la memoria, es un *tipo de referencia*.  
  
## Tipos de valor  
 Un tipo de datos es un *tipo de valores* si almacena los datos en su propia asignación de memoria.  Los tipos de valor incluyen lo siguiente:  
  
-   Todos los tipos de datos numéricos  
  
-   `Boolean`, `Char` y `Date`  
  
-   Todas las estructuras, incluso si sus miembros son tipos de referencia  
  
-   Las enumeraciones, ya que su tipo subyacente es siempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` o `ULong`  
  
 Cada estructura es un tipo de valor, aunque contiene miembros de tipo de referencia.  Por esta razón, las estructuras de .NET Framework implementan los tipos de valor como `Char` y `Integer` .  
  
 Se puede declarar un tipo de valor utilizando la palabra clave reservada, por ejemplo, `Decimal`.  También puede utilizar la palabra clave `New` para inicializar un tipo de valor.  Esto es especialmente útil si el tipo tiene un constructor que toma parámetros.  Un ejemplo de esto es el constructor <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> que compila un nuevo valor `Decimal` de las partes proporcionadas.  
  
## Tipos de referencia  
 Un *tipo de referencia* contiene un puntero a otra ubicación de memoria que almacena los datos.  Los tipos de referencia incluyen lo siguiente:  
  
-   `String`  
  
-   Todas las matrices, incluso si sus elementos son tipos de valor  
  
-   Los tipos de clase, como <xref:System.Windows.Forms.Form>  
  
-   Delegados  
  
 Una clase es un *tipo de referencia*.  Por este motivo, los tipos de referencia como `Object` y `String` son admitidos por clases de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)].  Observe que cada matriz es un tipo de referencia, aunque sus miembros sean tipos de valor.  
  
 Como un tipo de referencia representa una clase subyacente de.NET Framework, debe utilizar la palabra clave de [New \(Operador\)](../../../../visual-basic/language-reference/operators/new-operator.md) cuando se inicializa.  La instrucción siguiente inicializa una matriz.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## Elementos que no son tipos  
 Los elementos de programación siguientes no se califican como tipos porque no es posible especificar ninguno de ellos como tipo de datos para un elemento declarado:  
  
-   Espacios de nombres  
  
-   Módulos  
  
-   Eventos  
  
-   Propiedades y procedimientos  
  
-   Variables, constantes y campos  
  
## Trabajar con el tipo de datos Object  
 Puede asignar indistintamente un tipo de referencia o un tipo de valores a una variable del tipo de datos `Object`.  Una variable `Object` siempre contiene un puntero a los datos, nunca los propios datos.  Sin embargo, si se asigna un tipo de valor a una variable `Object`, ésta se comporta como si contuviera sus propios datos.  Para obtener más información, vea [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Puede averiguar si una variable de `Object` actúa como un tipo de referencia o un tipo de valor al método de <xref:Microsoft.VisualBasic.Information.IsReference%2A> en la clase de <xref:Microsoft.VisualBasic.Information> de espacio de nombres de <xref:Microsoft.VisualBasic?displayProperty=fullName> .  <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName> devuelve `True` si el contenido de la variable de `Object` representa un tipo de referencia.  
  
## Vea también  
 [Tipos de valor que aceptan valores NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structure \(Instrucción\)](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Uso eficiente de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)