---
title: Implementación de IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266916"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Tutorial: Implementar IEnumerable(Of T) en Visual Basic
La <xref:System.Collections.Generic.IEnumerable%601> interfaz se implementa mediante clases que pueden devolver una secuencia de valores de un elemento a la vez. La ventaja de devolver datos de un elemento a la vez es que no es necesario cargar el conjunto completo de datos en la memoria para trabajar con él. Sólo tiene que utilizar suficiente memoria para cargar un único elemento de los datos. Las clases `IEnumerable(T)` que implementan `For Each` la interfaz se pueden usar con bucles o consultas LINQ.  
  
 Por ejemplo, considere una aplicación que debe leer un archivo de texto grande y devolver cada línea del archivo que coincida con criterios de búsqueda concretos. La aplicación usa una consulta LINQ para devolver líneas del archivo que coinciden con los criterios especificados. Para consultar el contenido del archivo mediante una consulta LINQ, la aplicación podría cargar el contenido del archivo en una matriz o una colección. Sin embargo, cargar todo el archivo en una matriz o colección consumiría mucha más memoria de la necesaria. En su lugar, la consulta LINQ podría consultar el contenido del archivo mediante una clase enumerable, devolviendo solo los valores que coinciden con los criterios de búsqueda. Las consultas que devuelven solo unos pocos valores coincidentes consumirían mucha menos memoria.  
  
 Puede crear una clase que <xref:System.Collections.Generic.IEnumerable%601> implemente la interfaz para exponer los datos de origen como datos enumerables. La clase que `IEnumerable(T)` implementa la interfaz requerirá <xref:System.Collections.Generic.IEnumerator%601> otra clase que implemente la interfaz para recorrer en iteración los datos de origen. Estas dos clases permiten devolver elementos de datos secuencialmente como un tipo específico.  
  
 En este tutorial, creará una clase `IEnumerable(Of String)` que implementa la interfaz `IEnumerator(Of String)` y una clase que implementa la interfaz para leer un archivo de texto una línea a la vez.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Creación de la clase Enumerable  
  
**Cree el proyecto de clase enumerable**

1. En Visual Basic, en el menú **Archivo,** seleccione **Nuevo** y, a continuación, haga clic en **Proyecto**.

1. En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**. Seleccione **Biblioteca de clases** en el panel **Plantillas**. En el cuadro **Nombre**, escriba `StreamReaderEnumerable` y haga clic en **Aceptar**. Se muestra el nuevo proyecto.

1. En el **Explorador**de soluciones , haga clic con el botón secundario en el archivo Class1.vb y haga clic en **Cambiar nombre**. Cambie el nombre del archivo a `StreamReaderEnumerable.vb` y pulse ENTRAR. Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `StreamReaderEnumerable`. Esta clase implementará la interfaz `IEnumerable(Of String)`.

1. Haga clic con el botón secundario en el proyecto StreamReaderEnumerable, seleccione **Agregar**y, a continuación, haga clic en **Nuevo elemento**. Seleccione la plantilla **Clase.** En el cuadro **Nombre**, escriba `StreamReaderEnumerator.vb` y haga clic en **Aceptar**.

 La primera clase de este proyecto es la `IEnumerable(Of String)` clase enumerable e implementará la interfaz. Esta interfaz genérica <xref:System.Collections.IEnumerable> implementa la interfaz y garantiza que los `String`consumidores de esta clase pueden tener acceso a los valores escritos como .  
  
**Agregue el código para implementar IEnumerable**

1. Abra el archivo StreamReaderEnumerable.vb.

2. En la `Public Class StreamReaderEnumerable`línea siguiente , escriba lo siguiente y presione ENTRAR.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic rellena automáticamente la clase con los `IEnumerable(Of String)` miembros requeridos por la interfaz.
  
3. Esta clase enumerable leerá líneas de un archivo de texto una línea a la vez. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. La implementación <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> del `IEnumerable(Of String)` método de la interfaz `StreamReaderEnumerator` devolverá una nueva instancia de la clase. Se puede `GetEnumerator` realizar `IEnumerable` `Private`la implementación del método de la interfaz, ya que solo tiene que exponer los miembros de la `IEnumerable(Of String)` interfaz. Reemplace el código que Visual `GetEnumerator` Basic generó para los métodos con el código siguiente.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Agregue el código para implementar IEnumerator**

1. Abra el archivo StreamReaderEnumerator.vb.

2. En la `Public Class StreamReaderEnumerator`línea siguiente , escriba lo siguiente y presione ENTRAR.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic rellena automáticamente la clase con los `IEnumerator(Of String)` miembros requeridos por la interfaz.

3. La clase enumerador abre el archivo de texto y realiza la E/S del archivo para leer las líneas del archivo. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada y abra el archivo de texto para su lectura.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. Las `Current` propiedades de `IEnumerator(Of String)` `IEnumerator` las interfaces y y de las `String`interfaces devuelven el elemento actual del archivo de texto como un archivo . La implementación `Current` de `IEnumerator` la propiedad `Private`de la interfaz se puede `IEnumerator(Of String)` realizar, porque tiene que exponer solo los miembros de la interfaz. Reemplace el código que Visual `Current` Basic generó para las propiedades con el código siguiente.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. El `MoveNext` método `IEnumerator` de la interfaz navega al siguiente elemento del archivo de `Current` texto y actualiza el valor devuelto por la propiedad. Si no hay más elementos `MoveNext` para `False`leer, el método devuelve ; de `MoveNext` lo `True`contrario, el método devuelve . Agregue el siguiente código al método `MoveNext`.

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. El `Reset` método `IEnumerator` de la interfaz indica al iterador que apunte al inicio del archivo de texto y borra el valor del elemento actual. Agregue el siguiente código al método `Reset`.

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. El `Dispose` método `IEnumerator` de la interfaz garantiza que todos los recursos no administrados se liberan antes de que se destruya el iterador. El identificador de archivo `StreamReader` que utiliza el objeto es un recurso no administrado y debe cerrarse antes de que se destruya la instancia de iterador. Reemplace el código que Visual `Dispose` Basic generó para el método con el código siguiente.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>Uso del iterador de muestra

 Puede usar una clase enumerable en el código junto con estructuras de control que requieren un objeto que `IEnumerable`implemente, como un `For Next` bucle o una consulta LINQ. En el ejemplo `StreamReaderEnumerable` siguiente se muestra en una consulta LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For Each...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
