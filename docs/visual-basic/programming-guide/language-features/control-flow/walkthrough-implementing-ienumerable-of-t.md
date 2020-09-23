---
title: Implementar IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: f1f0036c38299f2392f8c8705e67b7bb6b7db068
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058643"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Tutorial: Implementar IEnumerable(Of T) en Visual Basic

La <xref:System.Collections.Generic.IEnumerable%601> interfaz la implementan las clases que pueden devolver una secuencia de valores de un elemento cada vez. La ventaja de devolver datos de un elemento a la vez es que no es necesario cargar el conjunto de datos completo en la memoria para trabajar con él. Solo tiene que usar la memoria suficiente para cargar un solo elemento de los datos. Las clases que implementan la `IEnumerable(T)` interfaz se pueden utilizar con `For Each` bucles o consultas LINQ.  
  
 Por ejemplo, considere una aplicación que debe leer un archivo de texto grande y devolver cada línea del archivo que coincida con criterios de búsqueda determinados. La aplicación usa una consulta LINQ para devolver las líneas del archivo que coinciden con los criterios especificados. Para consultar el contenido del archivo mediante una consulta LINQ, la aplicación podría cargar el contenido del archivo en una matriz o una colección. Sin embargo, cargar el archivo completo en una matriz o colección consumiría mucha más memoria de la necesaria. En su lugar, la consulta LINQ podría consultar el contenido del archivo mediante una clase Enumerable, devolviendo solo los valores que coinciden con los criterios de búsqueda. Las consultas que devuelven solo unos pocos valores coincidentes consumirán mucha menos memoria.  
  
 Puede crear una clase que implemente la <xref:System.Collections.Generic.IEnumerable%601> interfaz para exponer los datos de origen como datos enumerables. La clase que implementa la `IEnumerable(T)` interfaz requerirá otra clase que implemente la <xref:System.Collections.Generic.IEnumerator%601> interfaz para recorrer en iteración los datos de origen. Estas dos clases permiten devolver elementos de datos secuencialmente como un tipo específico.  
  
 En este tutorial, creará una clase que implementa la `IEnumerable(Of String)` interfaz y una clase que implementa la `IEnumerator(Of String)` interfaz para leer un archivo de texto línea a línea.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Crear la clase Enumerable  
  
**Crear el proyecto de clase Enumerable**

1. En Visual Basic, en el menú **archivo** , seleccione **nuevo** y haga clic en **proyecto**.

1. En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**. Seleccione **Biblioteca de clases** en el panel **Plantillas**. En el cuadro **Nombre**, escriba `StreamReaderEnumerable` y haga clic en **Aceptar**. Se muestra el nuevo proyecto.

1. En **Explorador de soluciones**, haga clic con el botón secundario en el archivo Class1. VB y haga clic en **cambiar nombre**. Cambie el nombre del archivo a `StreamReaderEnumerable.vb` y pulse ENTRAR. Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `StreamReaderEnumerable`. Esta clase implementará la interfaz `IEnumerable(Of String)`.

1. Haga clic con el botón secundario en el proyecto StreamReaderEnumerable, seleccione **Agregar**y, a continuación, haga clic en **nuevo elemento**. Seleccione la plantilla **clase** . En el cuadro **Nombre**, escriba `StreamReaderEnumerator.vb` y haga clic en **Aceptar**.

 La primera clase de este proyecto es la clase Enumerable e implementará la `IEnumerable(Of String)` interfaz. Esta interfaz genérica implementa la <xref:System.Collections.IEnumerable> interfaz y garantiza que los consumidores de esta clase puedan tener acceso a los valores con tipo `String` .  
  
**Agregar el código para implementar IEnumerable**

1. Abra el archivo StreamReaderEnumerable. VB.

2. En la línea después de `Public Class StreamReaderEnumerable` , escriba lo siguiente y presione Entrar.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic rellena automáticamente la clase con los miembros que requiere la `IEnumerable(Of String)` interfaz.
  
3. Esta clase Enumerable leerá las líneas de un archivo de texto una línea a la vez. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. La implementación del <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> método de la `IEnumerable(Of String)` interfaz devolverá una nueva instancia de la `StreamReaderEnumerator` clase. `GetEnumerator`Se puede realizar la implementación del método de la `IEnumerable` interfaz `Private` , porque solo tiene que exponer miembros de la `IEnumerable(Of String)` interfaz. Reemplace el código que Visual Basic genera para los `GetEnumerator` métodos con el código siguiente.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Agregar el código para implementar IEnumerator**

1. Abra el archivo StreamReaderEnumerator. VB.

2. En la línea después de `Public Class StreamReaderEnumerator` , escriba lo siguiente y presione Entrar.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic rellena automáticamente la clase con los miembros que requiere la `IEnumerator(Of String)` interfaz.

3. La clase de enumerador abre el archivo de texto y realiza la e/s de archivo para leer las líneas del archivo. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada y abrir el archivo de texto para leerlo.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. Las `Current` propiedades de las `IEnumerator(Of String)` interfaces y `IEnumerator` devuelven el elemento actual del archivo de texto como `String` . Se puede realizar la implementación de la `Current` propiedad de la `IEnumerator` interfaz `Private` , ya que tiene que exponer solo los miembros de la `IEnumerator(Of String)` interfaz. Reemplace el código que Visual Basic genera para las `Current` propiedades con el código siguiente.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. El `MoveNext` método de la `IEnumerator` interfaz navega al siguiente elemento del archivo de texto y actualiza el valor devuelto por la `Current` propiedad. Si no hay más elementos para leer, el `MoveNext` método devuelve `False` ; de lo contrario, el `MoveNext` método devuelve `True` . Agregue el código siguiente al método `MoveNext` .

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. El `Reset` método de la `IEnumerator` interfaz dirige el iterador para que apunte al inicio del archivo de texto y borra el valor del elemento actual. Agregue el código siguiente al método `Reset` .

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. El `Dispose` método de la `IEnumerator` interfaz garantiza que se liberen todos los recursos no administrados antes de que se destruya el iterador. El identificador de archivo que usa el `StreamReader` objeto es un recurso no administrado y debe cerrarse antes de que se destruya la instancia del iterador. Reemplace el código que Visual Basic generado para el `Dispose` método por el código siguiente.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>Usar el iterador de ejemplo

 Puede usar una clase Enumerable en el código junto con estructuras de control que requieran un objeto que implemente `IEnumerable` , como un `For Next` bucle o una consulta LINQ. En el ejemplo siguiente se muestra el `StreamReaderEnumerable` en una consulta LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../linq/introduction-to-linq.md)
- [Flujo de control](index.md)
- [Estructuras de bucle](loop-structures.md)
- [Instrucción For Each...Next](../../../language-reference/statements/for-each-next-statement.md)
