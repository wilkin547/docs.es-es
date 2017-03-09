---
title: "Tutorial: Implementar IEnumerable(Of T) en Visual Basic | Microsoft Docs"
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
  - "flujo de control"
  - "flujo de control [Visual Basic]"
  - "interfaces enumerables"
  - "estructuras de bucle, optimizar el rendimiento"
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Tutorial: Implementar IEnumerable(Of T) en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La interfaz <xref:System.Collections.Generic.IEnumerable%601> se implementa mediante clases que pueden devolver una secuencia de valores uno a uno.  La ventaja de devolver los datos uno a uno es que no es necesario cargar todo el conjunto de datos en la memoria para poder trabajar con él.  Solo tiene que usar la memoria suficiente para cargar un solo elemento de los datos.  Las clases que implementan la interfaz `IEnumerable(T)` se pueden usar con bucles `For Each` o consultas LINQ.  
  
 Por ejemplo, considere una aplicación que debe leer un archivo de texto grande y devolver cada una de las líneas del archivo que coincida con unos criterios de búsqueda determinados.  La aplicación usa una consulta LINQ para devolver las líneas del archivo que coinciden con los criterios especificados.  Para consultar el contenido del archivo mediante una consulta LINQ, la aplicación puede cargar el contenido del archivo en una matriz o una colección.  Sin embargo, al cargar el archivo completo en una matriz o colección se usaría mucha más memoria de la necesaria.  En su lugar, la consulta LINQ podría consultar el contenido del archivo mediante una clase enumerable, lo que devolvería solamente los valores que coincidan con los criterios de búsqueda.  Las consultas que solamente devuelven algunos valores coincidentes consumirían mucha menos memoria.  
  
 Puede crear una clase que implemente la interfaz <xref:System.Collections.Generic.IEnumerable%601> para exponer los datos de origen como datos enumerables.  La clase que implementa la interfaz `IEnumerable(T)` requerirá otra clase que implemente la interfaz <xref:System.Collections.Generic.IEnumerator%601> para recorrer en iteración los datos de origen.  Estas dos clases permiten devolver los elementos de datos secuencialmente como un tipo específico.  
  
 En este tutorial se creará una clase que implementa la interfaz `IEnumerable(Of String)` y otra que implementa la interfaz `IEnumerator(Of String)` para leer un archivo de texto de línea en línea.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## Crear la clase enumerable  
  
||  
|-|  
|Para crear el proyecto de clase enumerable|  
|1.  En el menú **Archivo** de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], seleccione **Nuevo** y haga clic en **Proyecto**.<br />2.  En el cuadro de diálogo **Nuevo proyecto**, en el panel **Tipos de proyecto**, asegúrese de haber seleccionado **Windows**.  En el panel **Plantillas**, seleccione **Biblioteca de clases**.  En el cuadro **Nombre**, escriba `StreamReaderEnumerable` y haga clic en **Aceptar**.  Aparecerá el proyecto nuevo.<br />3.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el archivo Class1.vb y haga clic en **Cambiar nombre**.  Cambie el nombre del archivo a `StreamReaderEnumerable.vb` y presione ENTRAR.  Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `StreamReaderEnumerable`.  Esta clase implementará la interfaz `IEnumerable(Of String)`.<br />4.  Haga clic con el botón secundario en el proyecto StreamReaderEnumerable, elija **Agregar** y haga clic en **Nuevo elemento**.  Seleccione la plantilla **Clase**.  En el cuadro **Nombre**, escriba `StreamReaderEnumerator.vb` y haga clic en **Aceptar**.|  
  
 La primera clase de este proyecto es la clase enumerable e implementará la interfaz `IEnumerable(Of String)`.  Esta interfaz genérica implementa la interfaz <xref:System.Collections.IEnumerable> y garantiza que los consumidores de esta clase puedan tener acceso a los valores de tipo `String`.  
  
||  
|-|  
|Para agregar el código para implementar IEnumerable|  
|1.  Abra el archivo StreamReaderEnumerable.vb.<br />2.  En la línea situada detrás de `Public Class StreamReaderEnumerable`, escriba lo siguiente y presione ENTRAR.<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#1)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] rellena automáticamente la clase con los miembros que requiere la interfaz `IEnumerable(Of String)`<br />3.  Esta clase enumerable leerá las líneas de un archivo de texto una a una.  Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada.<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#2)]<br />4.  La implementación del método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> de la interfaz `IEnumerable(Of String)` devolverá una nueva instancia de la clase `StreamReaderEnumerator`.  La implementación del método `GetEnumerator` de la interfaz `IEnumerable` puede ser de tipo `Private`, dado que solo se tienen que exponer los miembros de la interfaz `IEnumerable(Of String)`.  Reemplace el código generado por [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] para los métodos `GetEnumerator` con el siguiente código.<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#3)]|  
  
||  
|-|  
|Para agregar el código para implementar IEnumerator|  
|1.  Abra el archivo StreamReaderEnumerator.vb.<br />2.  En la línea situada detrás de `Public Class StreamReaderEnumerator`, escriba lo siguiente y presione ENTRAR.<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#4)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] rellena automáticamente la clase con los miembros que requiere la interfaz `IEnumerator(Of String)`<br />3.  La clase de enumerador abre el archivo de texto y realiza la E\/S del archivo para leer las líneas de este.  Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada y abrir el archivo de texto para su lectura.<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#5)]<br />4.  Las propiedades `Current` para las interfaces `IEnumerator(Of String)` e `IEnumerator` devuelven el elemento actual del archivo de texto como `String`.  La implementación de la propiedad `Current` de la interfaz `IEnumerator` puede ser de tipo `Private`, dado que solo se tienen que exponer los miembros de la interfaz `IEnumerator(Of String)`.  Reemplace el código generado por [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] para las propiedades `Current` con el siguiente código.<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#6)]<br />5.  El método `MoveNext` de la interfaz `IEnumerator` navega al siguiente elemento del archivo de texto y actualiza el valor devuelto por la propiedad `Current`.  Si no hay más elementos para leer, el método `MoveNext` devuelve `False`; de lo contrario, el método `MoveNext` devuelve `True`.  Agregue el código siguiente al método `MoveNext`.<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#7)]<br />6.  El método `Reset` de la interfaz `IEnumerator` dirige el iterador para que señale el inicio del archivo de texto y borra el valor del elemento actual.  Agregue el código siguiente al método `Reset`.<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#8)]<br />7.  El método `Dispose` de la interfaz `IEnumerator` garantiza la liberación de todos los recursos no administrados antes de destruirse el iterador.  El identificador de archivo que usa el objeto `StreamReader` es un recurso no administrado y se debe cerrar antes de que se destruya la instancia del iterador.  Reemplace el código generado por [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] para el método `Dispose` con el siguiente código.<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/StreamReaderIterator.vb#9)]|  
  
## Usar el iterador de ejemplo  
 En el código, se puede usar una clase enumerable junto con las estructuras de control que requieren un objeto que implementa `IEnumerable`, como un bucle `For Next` o una consulta LINQ.  En el ejemplo siguiente se muestra el objeto `StreamReaderEnumerable` en una consulta LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/visualbasic/VbVbalrIteratorWalkthrough/Module1.vb#10)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Estructuras de bucles](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For Each...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)