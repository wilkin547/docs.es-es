---
title: "Cómo: usar clases genéricas (Visual Basic) | Documentos de Microsoft"
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
- type parameters, defining
- data type arguments, defining
- arguments [Visual Basic], data types
- Of keyword, using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters, type
- types [Visual Basic], generic
- parameters, generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters, data type
- data type parameters, defining
- type arguments, defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
caps.latest.revision: 24
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
ms.openlocfilehash: eeb55be1c368e9ca80ab94de814a5e2ba9bc9f1f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-a-generic-class-visual-basic"></a>Cómo: Usar clases genéricas (Visual Basic)
Las clases que toman *parámetros de tipo* se denominan *clases genéricas*. Si usa una clase genérica, puede generar una *clase construida* a partir de ella proporcionando un *argumento de tipo* para cada uno de estos parámetros. Después, puede declarar una variable del tipo de clase construida, crear una instancia de la clase construida y asignarla a esa variable.  
  
 Además de clases, también puede definir y usar estructuras genéricas, interfaces, procedimientos y delegados.  
  
 En el procedimiento siguiente se toma una clase genérica definida en [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] y se crea una instancia a partir de ella.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Para usar una clase que toma un parámetro de tipo  
  
1.  Al principio del archivo de código fuente, incluya una [Imports (instrucción Namespace .NET y tipo)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para importar el <xref:System.Collections.Generic?displayProperty=fullName>espacio de nombres.</xref:System.Collections.Generic?displayProperty=fullName> Esto permite hacer referencia a la <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>clase sin tener que calificar por completo para diferenciarla de otras clases de cola como <xref:System.Collections.Queue?displayProperty=fullName>.</xref:System.Collections.Queue?displayProperty=fullName> </xref:System.Collections.Generic.Queue%601?displayProperty=fullName>  
  
2.  Cree el objeto de la manera normal, pero agregue `(Of` `type``)` inmediatamente después del nombre de clase.  
  
     En el ejemplo siguiente se utiliza la misma clase (<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>) para crear dos objetos de cola que contienen elementos de distintos tipos de datos.</xref:System.Collections.Generic.Queue%601?displayProperty=fullName> Agrega elementos al final de cada cola y, después, quita y muestra los elementos de la parte delantera de cada cola.  
  
     [!code-vb[VbVbalrDataTypes&#9;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/how-to-use-a-generic-class_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3)   
 [Of](../../../../visual-basic/language-reference/statements/of-clause.md)   
 [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Cómo: Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
