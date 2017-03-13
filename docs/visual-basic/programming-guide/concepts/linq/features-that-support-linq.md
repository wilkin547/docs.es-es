---
title: "Visual Basic Features That Support LINQ | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic, LINQ features"
  - "LINQ [Visual Basic], features supporting LINQ"
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 49
---
# Visual Basic Features That Support LINQ
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El nombre [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] hace referencia a la tecnología de Visual Basic que admite sintaxis de consulta y otras construcciones de lenguaje directamente en el lenguaje.  Con [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], no tiene que aprender un nuevo lenguaje para realizar consultas contra un origen de datos externo.  Puede realizar consultas contra datos de bases de datos relacionales, almacenes XML u objetos utilizando Visual Basic.  Esta integración de capacidades de consulta en el lenguaje permite comprobar, en tiempo de compilación, errores de sintaxis y seguridad de tipos.  Esta integración también le garantiza el conocimiento de los elementos esenciales para escribir consultas complejas y variadas en Visual Basic.  
  
 En las próximas secciones se describen las construcciones de lenguaje que admiten LINQ con suficiente detalle como para permitirle empezar a leer la documentación introductoria, ejemplos de código y aplicaciones de ejemplo.  También puede hacer clic en los vínculos para encontrar explicaciones más detalladas de cómo las características del lenguaje contribuyen a permitir las consultas integradas en el lenguaje.  Un buen lugar para empezar es [Tutorial: Escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## Expresiones de consulta  
 Las expresiones de consulta de Visual Basic se pueden expresar en una sintaxis declarativa similar a la de SQL o XQuery.  En tiempo de compilación, la sintaxis de consulta se convierte en llamadas a métodos en una implementación del proveedor LINQ de los métodos de extensión de operadores de consulta estándar.  Las aplicaciones controlan qué operadores de consulta estándar están dentro del ámbito especificando el espacio de nombres adecuado con una instrucción `Imports`.  La sintaxis para una expresión de consulta en Visual Basic es similar a ésta:  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Para obtener más información, vea [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## Variables con tipo implícito  
 En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, puede permitir al compilador deducir y asignar el tipo.  Esto se conoce como *inferencia de tipo de variable local*.  
  
 Las variables cuyos tipos se deducen son fuertemente tipadas, como las variables cuyo tipo se especifica explícitamente.  La inferencia de tipos de variable local solamente funciona cuando se define una variable local en el cuerpo de un método.  Para obtener más información, vea [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md) y [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 En el ejemplo siguiente se muestra la inferencia de tipos de variable local.  Para usar este ejemplo, debe establecer `Option Infer` en `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 La inferencia de tipo de variable local también permite crear tipos anónimos, que se describen más adelante en esta sección y son necesarios para las consultas LINQ.  
  
 En el ejemplo siguiente de LINQ, la inferencia de tipos se produce si `Option Infer` es `On` u `Off`.  Se producirá un error en tiempo de compilación si `Option Infer` es `Off` y `Option Strict` es `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## Inicializadores de objeto  
 Los inicializadores de objeto se utilizan en expresiones de consulta cuando se debe crear un tipo anónimo para albergar los resultados de una consulta.  También se pueden utilizar para inicializar objetos de tipos con nombre fuera de las consultas.  Utilizando un inicializador de objeto, puede inicializar un objeto en una sola línea sin llamar explícitamente a un constructor.  Suponiendo que tiene una clase denominada `Customer` con propiedades públicas `Name` y `Phone`, además de otras propiedades, un inicializador de objeto se puede utilizar de esta manera:  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Para obtener más información, vea [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## Tipos anónimos  
 Los tipos anónimos proporcionan una manera práctica de agrupar temporalmente un conjunto de propiedades en un elemento que se desea incluir en un resultado de la consulta.  Esto permite elegir cualquier combinación de campos disponibles en la consulta, en cualquier orden, sin definir un tipo de datos con nombre para el elemento.  
  
 El *tipo anónimo* lo construye dinámicamente el compilador.  El nombre del tipo es asignado por el compilador, y podría cambiar con cada nueva compilación.  Por tanto, el nombre no se puede utilizar directamente.  Los tipos anónimos se inicializan de la manera siguiente:  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Para obtener más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## Métodos de extensión.  
 Los métodos de extensión permiten agregar métodos a un tipo de datos o a una interfaz desde fuera de la definición.  Esta característica permite agregar nuevos métodos a un tipo existente sin tener que modificar el tipo.  Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan funcionalidad de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] para cualquier tipo que implementa <xref:System.Collections.Generic.IEnumerable%601>. Otras extensiones a <xref:System.Collections.Generic.IEnumerable%601> incluyen <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A> y <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 El siguiente método de extensión agrega un método de impresión a la clase <xref:System.String>.  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Al método se le llama como a un método de instancia ordinario de <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Para obtener más información, vea [métodos de extensión.](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## Expresiones lambda  
 Una expresión lambda es una función sin nombre que calcula y devuelve un solo valor.  A diferencia de las funciones con nombre, una expresión lambda se puede definir y ejecutar al mismo tiempo.  El ejemplo siguiente muestra 4.  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 Puede asignar la definición de la expresión lambda a un nombre de variable y, a continuación, utilizar el nombre para llamar a la función.  El ejemplo siguiente también muestra 4.  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 En [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], las expresiones lambda subyacen a muchos de los operadores de consulta estándar.  El compilador crea expresiones lambda para capturar los cálculos definidos en los métodos de consulta básicos como `Where`, `Select`, `Order By`, `Take While`, etc.  
  
 Por ejemplo, el código siguiente define una consulta que devuelve todos los alumnos de último curso de una lista de alumnos.  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 La definición de la consulta se compila en código similar al del ejemplo siguiente, el cual utiliza dos expresiones lambda para especificar los argumentos de `Where` y `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 Cualquiera de las versiones se puede ejecutar mediante un bucle `For Each`:  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Para obtener más información, vea [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## Vea también  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ y cadenas](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [C\# Features That Support LINQ](../../../../csharp/programming-guide/concepts/linq/features-that-support-linq.md)   
 [Option Infer \(instrucción\)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)