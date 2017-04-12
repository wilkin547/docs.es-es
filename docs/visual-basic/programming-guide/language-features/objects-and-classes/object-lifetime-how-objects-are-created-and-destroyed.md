---
title: "Duración de los objetos: Cómo se crean y destruyen (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Constructor
dev_langs:
- VB
helpviewer_keywords:
- destructors, object lifetime
- Sub Finalize destructor
- objects [Visual Basic], destroying
- lifetime, objects
- Sub New constructor, object lifetime
- Finalize method, object lifetime
- objects [Visual Basic], creating
- Class_Terminate
- Dispose method, object lifetime
- Class_Initialize
- object creation, object lifetime
- parameterized constructors
- objects [Visual Basic], lifetime
- objects [Visual Basic], garbage collection
- constructors [Visual Basic], object lifetime
- Sub Dispose destructor
- garbage collection, Visual Basic
ms.assetid: f1ee8458-b156-44e0-9a8a-5dd171648cd8
caps.latest.revision: 22
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
ms.openlocfilehash: 404c21c39a24d54c008fddf6dc386cc2895fe3a0
ms.lasthandoff: 03/13/2017

---
# <a name="object-lifetime-how-objects-are-created-and-destroyed-visual-basic"></a>Duración de los objetos: cómo se crean y destruyen (Visual Basic)
Mediante el uso de la palabra clave `New` se crea una instancia de una clase, un objeto. A menudo, las tareas de inicialización deben realizarse en los objetos nuevos antes de utilizarlos. Las tareas de inicialización comunes incluyen abrir archivos, conectarse a bases de datos y leer los valores de las claves del registro. Visual Basic controla la inicialización de objetos nuevos mediante procedimientos denominados *constructores* (métodos especiales que permiten controlar la inicialización).  
  
 Después de que un objeto abandone el ámbito, se libera por Common Language Runtime (CLR). Visual Basic controla la liberación de recursos del sistema mediante procedimientos denominados *destructores*. Juntos, los constructores y los destructores permiten la creación de bibliotecas de clases completas y predecibles.  
  
## <a name="using-constructors-and-destructors"></a>Usar constructores y destructores  
 Los constructores y los destructores controlan la creación y la destrucción de objetos. Los procedimientos `Sub New` y `Sub Finalize` de Visual Basic inicializan y destruyen objetos; sustituyen a los métodos `Class_Initialize` y `Class_Terminate` usados en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0 y versiones anteriores.  
  
### <a name="sub-new"></a>Sub New  
 El constructor `Sub New` solo puede ejecutarse una vez cuando se crea una clase. No se puede llamar explícitamente en ningún lugar que no sea la primera línea de código de otro constructor de la misma clase o de una clase derivada. Además, el código del método `Sub New` siempre se ejecuta antes que cualquier otro código en una clase. [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]y versiones posteriores crean implícitamente un `Sub New` constructor en tiempo de ejecución si no se define explícitamente un `Sub New` procedimiento para una clase.  
  
 Para crear un constructor para una clase, cree un procedimiento denominado `Sub New` en cualquier parte de la definición de clase. Para crear un constructor parametrizado, especifique los nombres y los tipos de datos de los argumentos en `Sub New` tal y como haría al especificar argumentos en cualquier otro procedimiento, como en el código siguiente:  
  
 [!code-vb[VbVbalrOOP&#42;](../../../../visual-basic/misc/codesnippet/VisualBasic/object-lifetime-how-objects-are-created-and-destroyed_1.vb)]  
  
 Los constructores suelen sobrecargarse con frecuencia, como en el código siguiente:  
  
 [!code-vb[VbVbalrOOP&#116;](../../../../visual-basic/misc/codesnippet/VisualBasic/object-lifetime-how-objects-are-created-and-destroyed_2.vb)]  
  
 Cuando defina una clase que derive de otra clase, la primera línea de un constructor debe ser una llamada al constructor de la clase base, a menos que la clase base tenga un constructor accesible que no tome ningún parámetro. Una llamada a la clase base que contiene el constructor anterior sería, por ejemplo, `MyBase.New(s)`. De lo contrario, `MyBase.New` es opcional, y el tiempo de ejecución de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] lo llama implícitamente.  
  
 Después de escribir el código para llamar al constructor del objeto primario, puede agregar código de inicialización al procedimiento `Sub New`. `Sub New` puede aceptar argumentos cuando se llama como constructor parametrizado. Estos parámetros se pasan desde el procedimiento que llama al constructor, por ejemplo, `Dim AnObject As New ThisClass(X)`.  
  
### <a name="sub-finalize"></a>Sub Finalize  
 Antes de liberar objetos, CLR llama automáticamente al método `Finalize` para los objetos que definen un procedimiento `Sub Finalize`. El método `Finalize` puede contener código que es necesario ejecutar inmediatamente antes de destruir un objeto, como el código para cerrar archivos y guardar información de estado. Hay una ligera disminución del rendimiento para la ejecución de `Sub Finalize`, por lo que se debe definir un método `Sub Finalize` solo cuando sea necesario liberar objetos explícitamente.  
  
> [!NOTE]
>  El recolector de elementos no utilizados en el CLR no (y no) desechar *no administrada de objetos*, objetos que el sistema operativo ejecuta directamente, fuera del entorno de CLR. Esto se debe a que los diferentes objetos no administrados deben eliminarse de maneras diferentes. Esta información no está directamente asociada con el objeto no administrado; debe buscarse en la documentación del objeto. Las clases que utilizan objetos no administrados deben eliminarlos en su método `Finalize`.  
  
 El destructor `Finalize` es un método protegido al que se puede llamar desde la clase a la que pertenece o desde clases derivadas. El sistema llama automáticamente a `Finalize` cuando se destruye un objeto, por lo que no debería llamar explícitamente a `Finalize` desde fuera de una implementación `Finalize` de una clase derivada.  
  
 A diferencia de `Class_Terminate`, que se ejecuta en cuanto un objeto se establece en Nothing, suele haber un retraso entre el momento en que un objeto pierde su ámbito y el momento en que Visual Basic llama al destructor `Finalize`. [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]y las versiones posteriores permiten un segundo tipo de destructor, <xref:System.IDisposable.Dispose%2A>, que puede llamar explícitamente en cualquier momento para liberar recursos inmediatamente.</xref:System.IDisposable.Dispose%2A>  
  
> [!NOTE]
>  Un destructor `Finalize` no debería producir excepciones, ya que la aplicación no puede controlarlas y eso puede hacer que la aplicación finalice.  
  
### <a name="how-new-and-finalize-methods-work-in-a-class-hierarchy"></a>Cómo funcionan los métodos New y Finalize en una jerarquía de clases  
 Siempre que se crea una instancia de una clase, Common Language Runtime (CLR) intenta ejecutar un procedimiento denominado `New`, si existe en ese objeto. `New` es un tipo de procedimiento llamado `constructor` que se utiliza para inicializar objetos nuevos antes de que se ejecute otro código en un objeto. Un constructor `New` puede utilizarse para abrir archivos, conectarse a bases de datos, inicializar variables y ocuparse de las demás tareas que deban realizarse para que pueda utilizarse un objeto.  
  
 Cuando se crea una instancia de una clase derivada, se ejecuta primero el constructor `Sub New` de la clase base, seguido de los constructores de las clases derivadas. Esto se debe a que la primera línea de código de un constructor `Sub New` utiliza la sintaxis `MyBase.New()` para llamar al constructor de la clase que se encuentra inmediatamente encima en la jerarquía de clases. A continuación, se llama al constructor `Sub New` para cada clase de la jerarquía de clases hasta que se alcanza el constructor de la clase base. En ese momento, se ejecuta el código en el constructor de la clase base, seguido del código en cada constructor de todas las clases derivadas y, en último lugar, se ejecuta el código de las clases más derivadas.  
  
 ![Constructores y herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/media/vaconstructorsinheritance.gif "vaConstructorsInheritance")  
  
 Cuando un objeto ya no es necesario, CLR llama el <xref:System.Object.Finalize%2A>método para ese objeto antes de liberar su memoria.</xref:System.Object.Finalize%2A> El <xref:System.Object.Finalize%2A>se llama al método un `destructor` ya que realiza tareas de limpieza, como guardar información de estado, cerrar archivos y conexiones a bases de datos y otras tareas que deben realizarse antes de liberar el objeto.</xref:System.Object.Finalize%2A>  
  
 ![Constructores y herencia&2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/media/vaconstructorsinheritance_2.gif "vaConstructorsInheritance_2")  
  
## <a name="idisposable-interface"></a>Interfaz IDisposable  
 Las instancias de clase suelen controlar los recursos no administrados por CLR, como identificadores de ventanas y conexiones de base de datos. Estos recursos deben eliminarse en el método `Finalize` de la clase, para que se liberen cuando el recolector de elementos no utilizados destruya el objeto. Sin embargo, el recolector de elementos no utilizados solo destruye objetos cuando CLR requiere más memoria libre. Esto significa que los recursos podrían no liberarse hasta mucho después de que el objeto haya salido del ámbito.  
  
 Para complementar la recolección de elementos, las clases pueden proporcionar un mecanismo para administrar activamente los recursos del sistema si implementan la <xref:System.IDisposable>interfaz.</xref:System.IDisposable> <xref:System.IDisposable>tiene un método, <xref:System.IDisposable.Dispose%2A>, que los clientes deben llamar cuando terminen de utilizar un objeto.</xref:System.IDisposable.Dispose%2A></xref:System.IDisposable> Puede usar el <xref:System.IDisposable.Dispose%2A>método para liberar recursos inmediatamente y realizar tareas como cerrar archivos y conexiones de base de datos.</xref:System.IDisposable.Dispose%2A> A diferencia de la `Finalize` destructor, el <xref:System.IDisposable.Dispose%2A>método no se llama automáticamente.</xref:System.IDisposable.Dispose%2A> Los clientes de una clase deben llamar explícitamente <xref:System.IDisposable.Dispose%2A>cuando desea liberar recursos inmediatamente.</xref:System.IDisposable.Dispose%2A>  
  
### <a name="implementing-idisposable"></a>Implementar IDisposable  
 Una clase que implementa el <xref:System.IDisposable>interfaz debería incluir estas secciones de código:</xref:System.IDisposable>  
  
-   Un campo para realizar un seguimiento de si se ha eliminado el objeto:  
  
    ```  
    Protected disposed As Boolean = False  
    ```  
  
-   Una sobrecarga de la <xref:System.IDisposable.Dispose%2A>que libera los recursos de la clase.</xref:System.IDisposable.Dispose%2A> Este método debe llamarse el <xref:System.IDisposable.Dispose%2A>y `Finalize` métodos de la clase base:</xref:System.IDisposable.Dispose%2A>  
  
    ```  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposed Then  
            If disposing Then  
                ' Insert code to free managed resources.  
            End If  
            ' Insert code to free unmanaged resources.  
        End If  
        Me.disposed = True  
    End Sub  
    ```  
  
-   Una implementación de <xref:System.IDisposable.Dispose%2A>que contiene sólo el código siguiente:</xref:System.IDisposable.Dispose%2A>  
  
    ```  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
    ```  
  
-   Un reemplazo del método `Finalize` que solo contenga el siguiente código:  
  
    ```  
    Protected Overrides Sub Finalize()  
        Dispose(False)  
        MyBase.Finalize()  
    End Sub  
    ```  
  
### <a name="deriving-from-a-class-that-implements-idisposable"></a>Derivar de una clase que implemente IDisposable  
 Una clase que deriva de una clase base que implementa el <xref:System.IDisposable>interfaz no necesita reemplazar ninguno de los métodos base a menos que utilice recursos adicionales que deban eliminarse.</xref:System.IDisposable> En ese caso, la clase derivada debe reemplazar el método `Dispose(disposing)` de la clase base para eliminar los recursos de la clase derivada. Este reemplazo debe llamar al método `Dispose(disposing)` de la clase base.  
  
```  
Protected Overrides Sub Dispose(ByVal disposing As Boolean)  
    If Not Me.disposed Then  
        If disposing Then  
            ' Insert code to free managed resources.  
        End If  
        ' Insert code to free unmanaged resources.  
    End If  
    MyBase.Dispose(disposing)  
End Sub  
```  
  
 Una clase derivada no debe reemplazar la clase base <xref:System.IDisposable.Dispose%2A>y `Finalize` métodos.</xref:System.IDisposable.Dispose%2A> Cuando se llama a dichos métodos desde una instancia de la clase derivada, la implementación de la clase base de los métodos llama al reemplazo de la clase derivada del método `Dispose(disposing)`.  
  
## <a name="garbage-collection-and-the-finalize-destructor"></a>Recolección de elementos no utilizados y el destructor Finalize  
 El [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] utiliza la *recolección de elementos no utilizados de seguimiento de referencias* sistema para liberar periódicamente los recursos. Visual Basic 6.0 y versiones anteriores utilizan un sistema diferente denominado *recuento de referencias* para administrar los recursos. Aunque ambos sistemas realizan la misma función automáticamente, existen algunas diferencias importantes.  
  
 CLR destruye periódicamente objetos cuando el sistema determina que ya no son necesarios. Los objetos se liberan más rápidamente cuando los recursos del sistema son escasos, y menos frecuentemente en caso contrario. El retraso que se produce entre el momento en que un objeto pierde su ámbito y el momento en que CLR lo libera conlleva que, a diferencia de lo que sucede con los objetos en Visual Basic 6.0 y versiones anteriores, no se puede determinar exactamente cuándo se destruirá el objeto. En tal situación, se dice que tiene los objetos *duración no determinista*. En la mayoría de los casos, la duración no determinista no cambia la manera de escribir las aplicaciones, siempre y cuando tenga en cuenta que el destructor `Finalize` puede no ejecutarse inmediatamente cuando un objeto pierde su ámbito.  
  
 Otra diferencia entre los sistemas de recolección de elementos no utilizados implica el uso de `Nothing`. Para aprovechar el recuento de referencias de Visual Basic 6.0 y versiones anteriores, los programadores a veces asignaban `Nothing` a variables de objetos para liberar las referencias que incluían dichas variables. Si la variable almacenaba la última referencia al objeto, los recursos del objeto se liberaban inmediatamente. En versiones posteriores de Visual Basic, aunque puede haber casos en los que este procedimiento todavía sea útil, su uso nunca hace que el objeto de referencia libere sus recursos inmediatamente. Para liberar inmediatamente los recursos, utilice el objeto <xref:System.IDisposable.Dispose%2A>(método), si está disponible.</xref:System.IDisposable.Dispose%2A> El único caso en el que una variable debe establecerse en `Nothing` es cuando su duración sea larga en comparación con el tiempo que tarda el recolector de elementos no utilizados en detectar objetos huérfanos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IDisposable.Dispose%2A></xref:System.IDisposable.Dispose%2A>   
 [Inicialización y finalización de componentes](http://msdn.microsoft.com/library/58444076-a9d2-4c91-b3f6-0e180dc0695d)   
 [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [Limpiar recursos no administrados](http://msdn.microsoft.com/library/a17b0066-71c2-4ba4-9822-8e19332fc213)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)
