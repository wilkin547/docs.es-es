---
title: Inicializadores de colección (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CollectionInitializer
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: a9290329-77b0-4fdf-ae75-8fc17287f469
ms.openlocfilehash: c22599f50ac071245a1381d267f3f7cb66806174
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45991628"
---
# <a name="collection-initializers-visual-basic"></a>Inicializadores de colección (Visual Basic)
Los *inicializadores de colección* proporcionan una sintaxis abreviada que permite crear una colección y rellenarla con un conjunto inicial de valores. Los inicializadores de colección son útiles cuando se crea una colección a partir de un conjunto de valores conocidos, como una lista de opciones de menú o categorías, un conjunto inicial de valores numéricos, una lista estática de cadenas como nombres de días o meses, o ubicaciones geográficas como una lista de estados usada para la validación.  
  
 Para más información sobre las colecciones, vea [Colecciones](../../../../visual-basic/programming-guide/concepts/collections.md).  
  
 Para identificar un inicializador de colección, use la palabra clave `From` seguida de llaves (`{}`). Esto es similar a la sintaxis de los literales de matriz que se describe en [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md) (Matrices). En los ejemplos siguientes se muestran varias maneras de usar inicializadores de colección para crear colecciones.  
  
 [!code-vb[VbVbalrCollectionInitializers#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#1)]  
  
> [!NOTE]
>  C# también proporciona inicializadores de colección. Los inicializadores de colección de C# proporcionan la misma funcionalidad que los inicializadores de colección de Visual Basic. Para obtener más información sobre los inicializadores de colección de C#, vea [Inicializadores de objeto y de colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="syntax"></a>Sintaxis  
 Un inicializador de colección consta de una lista de valores separados por comas que están entre llaves (`{}`), precedidos por la palabra clave `From`, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrCollectionInitializers#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#2)]  
  
 Cuando se crea una colección, como <xref:System.Collections.Generic.List%601> o <xref:System.Collections.Generic.Dictionary%602>, debe proporcionar el tipo de colección antes del inicializador de colección, como se muestra en el código siguiente.  
  
 [!code-vb[VbVbalrCollectionInitializers#13](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#13)]  
  
> [!NOTE]
>  No se puede combinar un inicializador de colección y un inicializador de objeto para inicializar el mismo objeto de colección. Puede usar inicializadores de objeto para inicializar objetos en un inicializador de colección.  
  
## <a name="creating-a-collection-by-using-a-collection-intializer"></a>Crear una colección mediante un inicializador de colección  
 Cuando crea una colección mediante un inicializador de colección, cada valor que se proporciona en el inicializador de colección se pasa al método `Add` correspondiente de la colección. Por ejemplo, si crea <xref:System.Collections.Generic.List%601> mediante un inicializador de colección, cada valor de cadena del inicializador de colección se pasa al método <xref:System.Collections.Generic.List%601.Add%2A>. Si quiere crear una colección mediante un inicializador de colección, el tipo especificado debe ser un tipo de colección válido. Las clases que implementan la interfaz <xref:System.Collections.Generic.IEnumerable%601> o que heredan la clase <xref:System.Collections.CollectionBase> son algunos ejemplos de tipos de colección válidos. El tipo especificado también debe exponer un método `Add` que cumpla los criterios siguientes.  
  
-   El método `Add` debe estar disponible en el ámbito en el que se llama al inicializador de colección. El método `Add` no tiene que ser público si el inicializador de colección se usa en un escenario en el que se puede obtener acceso a los métodos no públicos de la colección.  
  
-   El método `Add` debe ser un miembro de instancia o un miembro `Shared` de la clase de colección, o bien un método de extensión.  
  
-   Debe existir un método `Add` que se pueda asociar, en función de las reglas de resolución de sobrecarga, a los tipos que se proporcionan en el inicializador de colección.  
  
 Por ejemplo, en el ejemplo de código siguiente se muestra cómo se crea una colección `List(Of Customer)` mediante un inicializador de colección. Cuando se ejecuta el código, se pasa cada objeto `Customer` al método `Add(Customer)` de la lista genérica.  
  
 [!code-vb[VbVbalrCollectionInitializers#9](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#9)]  
  
 En el ejemplo de código siguiente se muestra código equivalente que no usa un inicializador de colección.  
  
 [!code-vb[VbVbalrCollectionInitializers#10](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#10)]  
  
 Si la colección tiene un método `Add` que tiene parámetros que coinciden con el constructor para el objeto `Customer`, los valores de parámetro para el método `Add` se pueden anidar dentro de inicializadores de colección, como se describe en la sección siguiente. Si la colección no tiene un método `Add`, puede crear uno como un método de extensión. Para obtener un ejemplo de cómo crear un método `Add` como un método de extensión para una colección, vea [How to: Create an Add Extension Method Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md) (Cómo: Crear un método de extensión Add usado por un inicializador de colección). Para obtener un ejemplo de cómo crear una colección personalizada que pueda usarse con un inicializador de colección, vea [How to: Create a Collection Used by a Collection Initializer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md) (Cómo: Crear una colección usada por un inicializador de colección).  
  
## <a name="nesting-collection-initializers"></a>Anidar inicializadores de colección  
 Puede anidar los valores de un inicializador de colección para identificar una sobrecarga específica de un método `Add` para la colección que se va a crear. Los valores pasados al método `Add` deben separarse con comas e incluirse entre llaves (`{}`), tal como se haría en un literal de matriz o un inicializador de colección.  
  
 Cuando se crea una colección mediante el uso de valores anidados, cada elemento de la lista de valores anidados se pasa como argumento al método `Add` que coincida con los tipos de elementos. Por ejemplo, en el ejemplo de código siguiente se crea un <xref:System.Collections.Generic.Dictionary%602> en que las claves son de tipo `Integer` y los valores son de tipo `String`. Cada una de las listas de valores anidados se asocia al método <xref:System.Collections.Generic.Dictionary%602.Add%2A> para el `Dictionary`.  
  
 [!code-vb[VbVbalrCollectionInitializers#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#5)]  
  
 El ejemplo de código anterior es equivalente al código siguiente.  
  
 [!code-vb[VbVbalrCollectionInitializers#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#6)]  
  
 Solo se envían listas de valores anidados del primer nivel de anidamiento al método `Add` del tipo de colección. Los niveles de anidamiento más profundos se tratan como literales de matriz y no habrá coincidencias de las listas de valores anidados con el método `Add` de ninguna colección.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|---|---|  
|[Crear un método de extensión Add usado por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)|Muestra cómo crear un método de extensión denominado `Add` que se puede usar para rellenar una colección con los valores de un inicializador de colección.|  
|[Crear una colección usada por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)|Muestra cómo habilitar el uso de un inicializador de colección mediante la inclusión de un método `Add` en una clase de colección que implementa `IEnumerable`.|  
  
## <a name="see-also"></a>Vea también

- [Colecciones](../../../../visual-basic/programming-guide/concepts/collections.md)  
- [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
- [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md)  
- [Propiedades autoimplementadas](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
- [Cómo: Inicializar una variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)  
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
- [Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
