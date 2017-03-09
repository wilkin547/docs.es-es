---
title: "C&#243;mo: Declarar un objeto usando un inicializador de objeto (Visual Basic) | Microsoft Docs"
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
  - "declarar objetos usando un inicializador de objetos"
  - "inicializadores [Visual Basic]"
  - "inicializadores de objeto [Visual Basic]"
  - "Temas "Cómo..." de vídeo, Visual Basic"
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# C&#243;mo: Declarar un objeto usando un inicializador de objeto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los inicializadores de objeto permiten declarar y crear instancias de una instancia de una clase en una sola instrucción.  Además, puede inicializar uno o más miembros de la instancia a la vez, sin invocar ningún constructor con parámetros.  
  
 Al utilizar un inicializador de objeto para crear una instancia de un tipo con nombre, se llama al constructor predeterminado de la clase, seguido de la inicialización de los miembros designados en el orden especificado.  
  
 El procedimiento siguiente muestra cómo crear una instancia de una clase `Student` de tres maneras diferentes.  La clase tiene, entre otros datos, el nombre, apellido y propiedades de año de clase.  Cada una de las tres declaraciones crea una nueva instancia de `Student`, con la propiedad `First` establecida en "Michael", la propiedad `Last` establecida en "Tucker" y todos los otros miembros establecidos en sus valores predeterminados.  El resultado de cada declaración del procedimiento es equivalente al ejemplo siguiente, que no utiliza ningún inicializador de objeto.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/how-to-declare-an-object_1.vb)]  
  
 Para obtener una implementación de la clase `Student`, vea [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  Puede copiar el código desde ese tema con el fin de configurar la clase y crear una lista de objetos `Student` con los que trabajar.  
  
### Para crear un objeto de una clase con nombre utilizando un inicializador de objeto  
  
1.  Comience la declaración como si pensara utilizar un constructor.  
  
     `Dim student1 As New Student`  
  
2.  Escriba la palabra clave `With`, seguida por una lista de inicializaciones entre llaves.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  En la lista de inicializaciones, incluya cada propiedad que desee inicializar y a la que desee asignar un valor inicial.  El nombre de la propiedad va precedido por un punto.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/how-to-declare-an-object_2.vb)]  
  
     Puede inicializar uno o más miembros de la clase.  
  
4.  O bien, puede declarar una nueva instancia de la clase y, a continuación, asignarle un valor.  Primero, declare una instancia de `Student`:  
  
     `Dim student2 As Student`  
  
5.  Comience la creación de una instancia de `Student` de la manera normal.  
  
     `Dim student2 As Student = New Student`  
  
6.  Escriba `With` y, a continuación, un inicializador de objeto para inicializar uno o más miembros de la nueva instancia.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/how-to-declare-an-object_3.vb)]  
  
7.  Puede simplificar la definición del paso anterior omitiendo `As Student`.  De esta forma, el compilador determina que `student3` es una instancia de `Student` utilizando la inferencia de tipo de variable local.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/how-to-declare-an-object_4.vb)]  
  
     Para obtener más información, vea [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## Vea también  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)   
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)