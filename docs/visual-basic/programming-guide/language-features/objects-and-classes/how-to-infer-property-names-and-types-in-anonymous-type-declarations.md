---
title: Filtrar Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: be3c74e8f8c69eb9f0a1d0dda4d6c90dfd7e567a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824733"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a>Filtrar Deducir tipos y nombres de propiedad en declaraciones de tipos anónimos (Visual Basic)
Los tipos anónimos no proporcionan ningún mecanismo para especificar directamente los tipos de datos de propiedades. Los tipos de todas las propiedades son inferidos. En el ejemplo siguiente, los tipos de `Name` y `Price` se infieren directamente de los valores que se usan para inicializarlos.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 Los tipos anónimos también pueden inferir nombres y tipos de propiedad de otros orígenes. En las secciones siguientes se ofrece una lista de las circunstancias donde es posible la inferencia y ejemplos de situaciones en que no lo es.  
  
## <a name="successful-inference"></a>Inferencia correcta  
  
#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a>Los tipos anónimos pueden inferir nombres y tipos de propiedad de los orígenes siguientes:  
  
-   Nombres de variables. El tipo anónimo `anonProduct` tendrá dos propiedades, `productName` y `productPrice`. Sus tipos de datos serán los de las variables originales, `String` y `Double`, respectivamente.  
  
     [!code-vb[VbVbalrAnonymousTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#11)]  
  
-   Nombres de campo o propiedad de otros objetos. Por ejemplo, considere un objeto `car` de un tipo `CarClass` que incluya las propiedades `Name` y `ID` . Para crear una nueva instancia de tipo anónimo, `car1`, con las propiedades `Name` y `ID` que se inicializan con los valores del objeto `car` , puede escribir lo siguiente:  
  
     [!code-vb[VbVbalrAnonymousTypes#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#34)]  
  
     La declaración anterior es equivalente a la línea más larga de código que define el tipo anónimo `car2`.  
  
     [!code-vb[VbVbalrAnonymousTypes#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#35)]  
  
-   Nombres de miembros XML.  
  
     [!code-vb[VbVbalrAnonymousTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#12)]  
  
     El tipo resultante de `anon` tendría una propiedad, `Book`, del tipo <xref:System.Collections.IEnumerable>(de XElement).  
  
-   Una función sin parámetros, como `SomeFunction` en el ejemplo siguiente.  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     La variable `anon2` en el código siguiente es un tipo anónimo que tiene una propiedad, un carácter denominado `First`. Este código mostrará una letra "E", la letra que devuelve la función <xref:System.Linq.Enumerable.First%2A>.  
  
     [!code-vb[VbVbalrAnonymousTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#13)]  
  
## <a name="inference-failures"></a>Errores de inferencia  
  
#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a>Se producirá un error en la inferencia de nombre en muchas circunstancias, incluidas las siguientes:  
  
-   La inferencia se deriva de la invocación de un método, un constructor o una propiedad con parámetros que requiere argumentos. La declaración anterior de `anon1` genera un error si `someFunction` tiene uno o más argumentos.  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     La asignación a un nuevo nombre de propiedad resuelve el problema.  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   La inferencia se deriva de una expresión compleja.  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     El error se puede resolver asignando el resultado de la expresión a un nombre de propiedad.  
  
     [!code-vb[VbVbalrAnonymousTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#14)]  
  
-   La inferencia de varias propiedades genera dos o más propiedades con el mismo nombre. Si nos referimos a las declaraciones de los ejemplos anteriores, no se pueden mostrar `product.Name` y `car1.Name` como propiedades del mismo tipo anónimo. Esto se debe a que el identificador inferido de cada uno de ellos sería `Name`.  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     El problema puede resolverse asignando los valores a distintos nombres de propiedad.  
  
     [!code-vb[VbVbalrAnonymousTypes#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#36)]  
  
     Observe que los cambios entre mayúsculas y minúsculas no forman dos nombres distintos.  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   El tipo y el valor iniciales de una propiedad dependen de otra propiedad que todavía no está establecida. Por ejemplo, `.IDName = .LastName` no es válido en una declaración de tipo anónimo, a menos que `.LastName` ya esté inicializado.  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     En este ejemplo, puede corregir el problema invirtiendo el orden en que las propiedades están declaradas.  
  
     [!code-vb[VbVbalrAnonymousTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#15)]  
  
-   Un nombre de propiedad del tipo anónimo es igual que el nombre de un miembro de <xref:System.Object>. Por ejemplo, la siguiente declaración genera un error porque `Equals` es un método de <xref:System.Object>.  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     Puede corregir el problema cambiando el nombre de propiedad:  
  
     [!code-vb[VbVbalrAnonymousTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#16)]  
  
## <a name="see-also"></a>Vea también

- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
