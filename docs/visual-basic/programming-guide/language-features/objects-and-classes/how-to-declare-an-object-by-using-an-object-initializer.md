---
title: 'Cómo: Declarar un objeto usando un inicializador de objeto'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347135"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Cómo: Declarar un objeto usando un inicializador de objeto (Visual Basic)
Los inicializadores de objeto permiten declarar y crear instancias de una instancia de una clase en una única instrucción. Además, puede inicializar uno o más miembros de la instancia al mismo tiempo, sin invocar un constructor con parámetros.  
  
 Cuando se usa un inicializador de objeto para crear una instancia de un tipo con nombre, se llama al constructor sin parámetros para la clase, seguido de la inicialización de los miembros designados en el orden que se especifique.  
  
 En el siguiente procedimiento se muestra cómo crear una instancia de una clase `Student` de tres maneras diferentes. La clase tiene las propiedades nombre, apellidos y año de clase, entre otras. Cada una de las tres declaraciones crea una nueva instancia de `Student`, con la propiedad `First` establecida en "Michael", la propiedad `Last` establecida en "Tucker" y todos los demás miembros establecidos en sus valores predeterminados. El resultado de cada declaración en el procedimiento es equivalente al ejemplo siguiente, que no usa un inicializador de objeto.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Para obtener una implementación de la clase `Student`, vea [Cómo: crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Puede copiar el código de ese tema para configurar la clase y crear una lista de `Student` objetos con los que trabajar.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Para crear un objeto de una clase con nombre mediante un inicializador de objeto  
  
1. Comience la declaración como si hubiera planeado utilizar un constructor.  
  
     `Dim student1 As New Student`  
  
2. Escriba la palabra clave `With`, seguida de una lista de inicialización entre llaves.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. En la lista de inicialización, incluya cada propiedad que desee inicializar y asígnele un valor inicial. El nombre de la propiedad va precedido de un punto.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     Puede inicializar uno o más miembros de la clase.  
  
4. Como alternativa, puede declarar una nueva instancia de la clase y, a continuación, asignarle un valor. En primer lugar, declare una instancia de `Student`:  
  
     `Dim student2 As Student`  
  
5. Comience la creación de una instancia de `Student` de la manera normal.  
  
     `Dim student2 As Student = New Student`  
  
6. Escriba `With` y, a continuación, un inicializador de objeto para inicializar uno o más miembros de la nueva instancia.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. Puede simplificar la definición en el paso anterior omitiendo `As Student`. Si lo hace, el compilador determina que `student3` es una instancia de `Student` mediante la inferencia de tipo local.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Para obtener más información, vea [inferencia de tipo local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>Vea también

- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
