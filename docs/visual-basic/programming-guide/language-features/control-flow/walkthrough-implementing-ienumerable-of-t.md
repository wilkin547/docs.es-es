---
title: Implementación de IEnumerable en Visual Basic
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: be2eefdc52d38df3071d457b7a71dbac6eaa2657
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739664"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Tutorial: Implementar IEnumerable(Of T) en Visual Basic
El <xref:System.Collections.Generic.IEnumerable%601> interfaz se implementa mediante las clases que pueden devolver una secuencia de valores uno a la vez. La ventaja de devolver los datos de un elemento a la vez es que no es necesario que cargar el conjunto completo de datos en memoria para trabajar con ella. Solo debe usar la memoria suficiente para cargar un único elemento de los datos. Las clases que implementan la `IEnumerable(T)` interfaz pueden utilizarse con `For Each` bucles o las consultas LINQ.  
  
 Por ejemplo, considere una aplicación que debe leer un archivo de texto grande y devolver cada línea del archivo que coincida con los criterios de búsqueda determinada. La aplicación usa una consulta LINQ para devolver las líneas del archivo que coinciden con los criterios especificados. Para consultar el contenido del archivo mediante el uso de una consulta LINQ, la aplicación podría cargar el contenido del archivo en una matriz o una colección. Sin embargo, cargar el archivo completo en una matriz o colección consumiría mucho más memoria que es necesario. La consulta LINQ en su lugar, podría consultar el contenido del archivo mediante el uso de una clase enumerable, devolver sólo los valores que coinciden con los criterios de búsqueda. Las consultas que devuelven solo unos pocos valores coincidentes consumiría mucho menos memoria.  
  
 Puede crear una clase que implementa el <xref:System.Collections.Generic.IEnumerable%601> interfaz para exponer los datos de origen como datos enumerables. La clase que implementa el `IEnumerable(T)` interfaz requerirá otra clase que implementa el <xref:System.Collections.Generic.IEnumerator%601> interfaz para recorrer en iteración el origen de datos. Estas dos clases permiten devolver elementos de datos de forma secuencial, como un tipo específico.  
  
 En este tutorial, creará una clase que implementa el `IEnumerable(Of String)` interfaz y una clase que implementa el `IEnumerator(Of String)` interfaz para leer un archivo de texto de línea a la vez.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Creación de la clase Enumerable  
  
**Crear el proyecto de la clase enumerable**

1.  En Visual Basic, en el **archivo** menú, elija **New** y, a continuación, haga clic en **proyecto**.

1.  En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, asegúrese de que esté seleccionado **Windows**. Seleccione **Biblioteca de clases** en el panel **Plantillas**. En el cuadro **Nombre**, escriba `StreamReaderEnumerable` y haga clic en **Aceptar**. Se muestra el nuevo proyecto.

1.  En **el Explorador de soluciones**, haga clic en el archivo Class1.vb y haga clic en **cambiar el nombre**. Cambie el nombre del archivo a `StreamReaderEnumerable.vb` y pulse ENTRAR. Al cambiar el nombre del archivo también se cambiará el nombre de la clase a `StreamReaderEnumerable`. Esta clase implementará la interfaz `IEnumerable(Of String)`.

1.  Haga clic en el proyecto StreamReaderEnumerable, elija **agregar**y, a continuación, haga clic en **nuevo elemento**. Seleccione el **clase** plantilla. En el **nombre** , escriba `StreamReaderEnumerator.vb` y haga clic en **Aceptar**.

 La primera clase en este proyecto es la clase enumerable y se implementará el `IEnumerable(Of String)` interfaz. Esta interfaz genérica implementa el <xref:System.Collections.IEnumerable> interfaz y garantiza que los consumidores de esta clase pueden tener acceso a valores de tipo `String`.  
  
**Agregue el código para implementar IEnumerable**

1. Abra el archivo StreamReaderEnumerable.vb.

2. En la línea que sigue `Public Class StreamReaderEnumerable`, escriba lo siguiente y presione ENTRAR.

   [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]

   Visual Basic se rellena automáticamente la clase con los miembros requeridos por la `IEnumerable(Of String)` interfaz.
  
3. Esta clase enumerable leerá las líneas de un archivo de texto de línea a la vez. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como un parámetro de entrada.

   [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]

4. La implementación de la <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> método de la `IEnumerable(Of String)` interfaz devolverá una nueva instancia de la `StreamReaderEnumerator` clase. La implementación de la `GetEnumerator` método de la `IEnumerable` interfaz puede realizarse `Private`, ya que tiene que exponer solo los miembros de la `IEnumerable(Of String)` interfaz. Reemplace el código que genera Visual Basic para el `GetEnumerator` métodos con el código siguiente.

   [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]  
  
**Agregue el código para implementar IEnumerator**

1. Abra el archivo StreamReaderEnumerator.vb.

2. En la línea que sigue `Public Class StreamReaderEnumerator`, escriba lo siguiente y presione ENTRAR.

   [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]

   Visual Basic se rellena automáticamente la clase con los miembros requeridos por la `IEnumerator(Of String)` interfaz.

3. La clase de enumerador abre el archivo de texto y realiza la E/S para leer las líneas del archivo de archivo. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como un parámetro de entrada y abra el archivo de texto para lectura.

   [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]

4. El `Current` propiedades tanto para el `IEnumerator(Of String)` y `IEnumerator` interfaces devuelven el elemento actual del archivo de texto como un `String`. La implementación de la `Current` propiedad de la `IEnumerator` interfaz puede realizarse `Private`, ya que tiene que exponer solo los miembros de la `IEnumerator(Of String)` interfaz. Reemplace el código que genera Visual Basic para el `Current` propiedades con el código siguiente.

   [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]

5. El `MoveNext` método de la `IEnumerator` interfaz navega al elemento siguiente en el archivo de texto y actualiza el valor devuelto por la `Current` propiedad. Si no hay ningún elemento para leer, más el `MoveNext` devuelve del método `False`; de lo contrario el `MoveNext` devuelve del método `True`. Agregue el código siguiente al método `MoveNext` .

   [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]

6. El `Reset` método de la `IEnumerator` interfaz dirige el iterador para que apunte al principio del archivo de texto y borra el valor del elemento actual. Agregue el código siguiente al método `Reset` .

   [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]

7. El `Dispose` método de la `IEnumerator` interfaz garantiza que se liberen todos los recursos no administrados antes de que se destruya el iterador. El identificador de archivo que usa el `StreamReader` objeto es un recurso no administrado y debe cerrarse antes de que se destruya la instancia del iterador. Reemplace el código que genera Visual Basic para el `Dispose` método con el código siguiente.

   [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)] 
  
## <a name="using-the-sample-iterator"></a>Mediante el iterador de ejemplo

 Puede usar la clase enumerable en el código junto con las estructuras de control que requieren un objeto que implementa `IEnumerable`, como un `For Next` bucle o una consulta LINQ. El ejemplo siguiente se muestra el `StreamReaderEnumerable` en una consulta LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [For Each...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
