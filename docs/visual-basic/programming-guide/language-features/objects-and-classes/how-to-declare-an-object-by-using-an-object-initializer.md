---
title: Procedimiento Declarar un objeto usando un inicializador de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 850e20fe8b5b6bfd392c80c87950a81a1a8a5c24
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755198"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Procedimiento Declarar un objeto usando un inicializador de objeto (Visual Basic)
Los inicializadores de objeto permiten declarar y crear una instancia de una clase en una sola instrucción. Además, puede inicializar a uno o varios miembros de la instancia al mismo tiempo, sin invocar un constructor parametrizado.  
  
 Cuando se usa un inicializador de objeto para crear una instancia de un tipo con nombre, se llama al constructor sin parámetros para la clase, seguido de la inicialización de los miembros designados en el orden que especifique.  
  
 El siguiente procedimiento muestra cómo crear una instancia de un `Student` clase de tres maneras diferentes. La clase tiene el nombre, apellido y propiedades de año de la clase, entre otros. Cada una de las tres declaraciones crea una nueva instancia de `Student`, con la propiedad `First` establecido en "Michael," propiedad `Last` establecida en "Tucker" y todos los demás miembros que se establezca en sus valores predeterminados. El resultado de cada declaración en el procedimiento es equivalente al ejemplo siguiente, que no usa a un inicializador de objeto.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Para obtener una implementación de la `Student` de clases, vea [Cómo: Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Puede copiar el código en ese tema para configurar la clase y crear una lista de `Student` para trabajar con los objetos.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Para crear un objeto de una clase con nombre mediante un inicializador de objeto  
  
1. Comience la declaración como si planea utilizar un constructor.  
  
     `Dim student1 As New Student`  
  
2. Escriba la palabra clave `With`, seguido de una lista de inicialización entre llaves.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. En la lista de inicialización, incluya cada propiedad que desea inicializar y asignarle un valor inicial. El nombre de la propiedad está precedido por un punto.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     Puede inicializar a uno o varios miembros de la clase.  
  
4. Como alternativa, puede declarar una nueva instancia de la clase y, a continuación, asignarle un valor. En primer lugar, declare una instancia de `Student`:  
  
     `Dim student2 As Student`  
  
5. Comience la creación de una instancia de `Student` de la manera normal.  
  
     `Dim student2 As Student = New Student`  
  
6. Tipo `With` y, a continuación, un inicializador de objeto para inicializar uno o varios miembros de la nueva instancia.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. Puede simplificar la definición en el paso anterior omitiendo `As Student`. Si lo hace, el compilador determina que `student3` es una instancia de `Student` mediante el uso de la inferencia de tipo local.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Para obtener más información, consulte [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>Vea también

- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Cómo: Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
