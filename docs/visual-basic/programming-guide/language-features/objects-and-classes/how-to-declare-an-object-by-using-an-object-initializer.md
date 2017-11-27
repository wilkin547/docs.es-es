---
title: "Cómo: Declarar un objeto usando un inicializador de objeto (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 87c818765cbeac7a3080ee666d464052493e5bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Cómo: Declarar un objeto usando un inicializador de objeto (Visual Basic)
Inicializadores de objeto permiten declarar y crear una instancia de una clase en una sola instrucción. Además, puede inicializar a uno o varios miembros de la instancia a la vez, sin invocar un constructor con parámetros.  
  
 Cuando se usa un inicializador de objeto para crear una instancia de un tipo con nombre, se llama al constructor predeterminado para la clase, seguido de inicialización de los miembros designados en el orden que especifique.  
  
 El siguiente procedimiento muestra cómo crear una instancia de un `Student` clase de tres maneras diferentes. La clase contiene el nombre, apellido y propiedades de año de la clase, entre otros. Cada una de las tres declaraciones crea una nueva instancia de `Student`, con la propiedad `First` establecida en "Michael", la propiedad `Last` establecida en "Tucker" y todos los otros miembros establecidos en sus valores predeterminados. El resultado de cada declaración en el procedimiento es equivalente al ejemplo siguiente, que no usa a un inicializador de objeto.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 Para obtener una implementación de la `Student` de clases, consulte [Cómo: crear una lista de elementos de](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Puede copiar el código de ese tema para configurar la clase y crear una lista de `Student` objetos que se va a trabajar con.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Para crear un objeto de una clase con nombre usando un inicializador de objeto  
  
1.  Comience la declaración como si planea utilizar un constructor.  
  
     `Dim student1 As New Student`  
  
2.  Escriba la palabra clave `With`, seguido de una lista de inicialización entre llaves.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  En la lista de inicializaciones, incluya cada propiedad que desea inicializar y asígnele un valor inicial. El nombre de la propiedad está precedido por un punto.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     Puede inicializar a uno o varios miembros de la clase.  
  
4.  Como alternativa, puede declarar una nueva instancia de la clase y, a continuación, asignar un valor a él. Primero, declare una instancia de `Student`:  
  
     `Dim student2 As Student`  
  
5.  Iniciar la creación de una instancia de `Student` de la forma habitual.  
  
     `Dim student2 As Student = New Student`  
  
6.  Tipo de `With` y, a continuación, un inicializador de objeto para inicializar uno o varios miembros de la nueva instancia.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  Puede simplificar la definición en el paso anterior omitiendo `As Student`. Si lo hace, el compilador determina que `student3` es una instancia de `Student` mediante el uso de la inferencia de tipo local.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     Para obtener más información, consulte [inferencia de tipo Local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>Vea también  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
