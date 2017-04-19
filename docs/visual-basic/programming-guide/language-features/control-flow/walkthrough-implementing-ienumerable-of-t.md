---
title: Implementar IEnumerable en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures, optimizing performance
- control flow
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 68c37c46cbceb1056d50972cdc58ddb7c7577447
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Tutorial: Implementar IEnumerable(Of T) en Visual Basic
El <xref:System.Collections.Generic.IEnumerable%601>se implementa mediante clases que pueden devolver una secuencia de valores uno a la vez.</xref:System.Collections.Generic.IEnumerable%601> La ventaja de devolver los datos de un elemento a la vez es que no es necesario cargar todo el conjunto de datos en la memoria para trabajar con él. Solo debe usar la memoria suficiente para cargar un solo elemento de los datos. Las clases que implementan la `IEnumerable(T)` interfaz se puede utilizar con `For Each` bucles o consultas LINQ.  
  
 Por ejemplo, considere una aplicación que debe leer un archivo de texto grande y devolver cada línea del archivo que coincide con los criterios de búsqueda determinada. La aplicación usa una consulta LINQ para devolver las líneas del archivo que coinciden con los criterios especificados. Para consultar el contenido del archivo mediante una consulta LINQ, la aplicación podría cargar el contenido del archivo en una matriz o una colección. Sin embargo, consumirá mucho más memoria que es necesario cargar todo el archivo en una matriz o colección. La consulta LINQ en su lugar podría consultar el contenido del archivo mediante una clase enumerable, devolver solo los valores que coinciden con los criterios de búsqueda. Las consultas que solamente devuelven algunos valores coincidentes consumirían mucha menos memoria.  
  
 Puede crear una clase que implementa el <xref:System.Collections.Generic.IEnumerable%601>interfaz para exponer los datos de origen como datos enumerables.</xref:System.Collections.Generic.IEnumerable%601> La clase que implementa el `IEnumerable(T)` interfaz requerirá otra clase que implementa el <xref:System.Collections.Generic.IEnumerator%601>interfaz para recorrer en iteración el origen de datos.</xref:System.Collections.Generic.IEnumerator%601> Estas dos clases permiten devolver elementos de datos secuencialmente como un tipo específico.  
  
 En este tutorial, creará una clase que implementa el `IEnumerable(Of String)` interfaz y una clase que implementa el `IEnumerator(Of String)` interfaz para leer un archivo una línea de texto a la vez.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Creación de la clase Enumerable  
  
|Para crear el proyecto de clase enumerable|  
|---|  
|1.  En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], en la **archivo** menú, seleccione **nueva** y, a continuación, haga clic en **proyecto**.<br />2.  En el **nuevo proyecto** cuadro de diálogo el **tipos de proyecto** panel, asegúrese de que **Windows** está seleccionada. Seleccione **biblioteca de clases de** en el **plantillas** panel. En el **nombre** , escriba `StreamReaderEnumerable`y, a continuación, haga clic en **Aceptar**. Se muestra el nuevo proyecto.<br />3.  En **el Explorador de soluciones**, haga clic en el archivo Class1.vb y haga clic en **cambiar el nombre de**. El nombre del archivo a `StreamReaderEnumerable.vb` y presione ENTRAR. Cambiar el nombre del archivo cambiará también la clase `StreamReaderEnumerable`. Esta clase implementará la `IEnumerable(Of String)` interfaz.<br />4.  Haga clic en el proyecto StreamReaderEnumerable, elija **agregar**y, a continuación, haga clic en **nuevo elemento**. Seleccione el **clase** plantilla. En el **nombre** , escriba `StreamReaderEnumerator.vb` y haga clic en **Aceptar**.|  
  
 La primera clase de este proyecto es la clase enumerable y se implementará el `IEnumerable(Of String)` interfaz. Esta interfaz genérica implementa el <xref:System.Collections.IEnumerable>interfaz y las garantías de que los consumidores de esta clase pueden tener acceso a los valores de tipo `String`.</xref:System.Collections.IEnumerable>  
  
|Para agregar el código para implementar IEnumerable|  
|---|  
|1.  Abra el archivo StreamReaderEnumerable.vb.<br />2.  En la línea después de `Public Class StreamReaderEnumerable`, escriba lo siguiente y presione ENTRAR.<br />     [!code-vb[1 VbVbalrIteratorWalkthrough](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]rellena automáticamente la clase con los miembros requeridos por la `IEnumerable(Of String)` interfaz.<br />3.  Esta clase enumerable leerá las líneas de un archivo una línea de texto a la vez. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#2;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  La implementación de la <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>método de la `IEnumerable(Of String)` interfaz devolverá una nueva instancia de la `StreamReaderEnumerator` clase</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> La implementación de la `GetEnumerator` método de la `IEnumerable` interfaz se puede realizar `Private`, ya que tiene que exponer sólo los miembros de la `IEnumerable(Of String)` interfaz. Reemplace el código que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generado para el `GetEnumerator` métodos con el código siguiente.<br />     [!code-vb[VbVbalrIteratorWalkthrough&3;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|Para agregar el código para implementar IEnumerator|  
|---|  
|1.  Abra el archivo StreamReaderEnumerator.vb.<br />2.  En la línea después de `Public Class StreamReaderEnumerator`, escriba lo siguiente y presione ENTRAR.<br />     [!code-vb[VbVbalrIteratorWalkthrough Nº&4;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]rellena automáticamente la clase con los miembros requeridos por la `IEnumerator(Of String)` interfaz.<br />3.  La clase de enumerador abre el archivo de texto y realiza la E/S de archivo para leer las líneas del archivo. Agregue el código siguiente a la clase para exponer un constructor público que toma una ruta de acceso de archivo como parámetro de entrada y abra el archivo de texto para lectura.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#5;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  El `Current` propiedades tanto para la `IEnumerator(Of String)` y `IEnumerator` interfaces devuelven el elemento actual del archivo de texto como un `String`. La implementación de la `Current` propiedad de la `IEnumerator` interfaz se puede realizar `Private`, ya que tiene que exponer sólo los miembros de la `IEnumerator(Of String)` interfaz. Reemplace el código que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generado para el `Current` propiedades con el código siguiente.<br />     [!code-vb[VbVbalrIteratorWalkthrough Nº&6;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  El `MoveNext` método de la `IEnumerator` interfaz se desplaza al siguiente elemento del archivo de texto y actualiza el valor devuelto por el `Current` propiedad. Si no hay ningún elemento para leer, más el `MoveNext` método devuelve `False`; de lo contrario la `MoveNext` método devuelve `True`. Agregue el código siguiente al método `MoveNext`.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#7;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  El `Reset` método de la `IEnumerator` interfaz dirige el iterador para que apunte al principio del archivo de texto y borra el valor del elemento actual. Agregue el código siguiente al método `Reset`.<br />     [!code-vb[VbVbalrIteratorWalkthrough Nº&8;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  El `Dispose` método de la `IEnumerator` interfaz garantiza que se liberan todos los recursos no administrados antes de destruirse el iterador. El identificador de archivo utilizado por el `StreamReader` objeto es un recurso no administrado y deben cerrarse antes de que se destruye la instancia del iterador. Reemplace el código que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generado para el `Dispose` método por el código siguiente.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#9;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>Usar el iterador de ejemplo  
 Puede usar una clase enumerable en el código junto con estructuras de control que requieren un objeto que implementa `IEnumerable`, como un `For Next` bucle o una consulta LINQ. El ejemplo siguiente se muestra el `StreamReaderEnumerable` en una consulta LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough&#10;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For Each...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

