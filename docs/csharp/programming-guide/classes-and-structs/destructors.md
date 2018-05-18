---
title: Finalizadores (Guía de programación de C#)
ms.date: 05/10/2017
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: fc15818883736015419f8599d482185bbab5120a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="finalizers-c-programming-guide"></a>Finalizadores (Guía de programación de C#)
Los finalizadores se usan para destruir instancias de clases.  
  
## <a name="remarks"></a>Comentarios  
  
-   Los finalizadores no se pueden definir en structs. Solo se usan con clases.  
  
-   Una clase solo puede tener un finalizador.  
  
-   Los finalizadores no se pueden heredar ni sobrecargar.  
  
-   No se puede llamar a los finalizadores. Se invocan automáticamente.  
  
-   Un finalizador no permite modificadores ni tiene parámetros.  
  
 Por ejemplo, el siguiente código muestra una declaración de un finalizador para la clase `Car`.
  
 [!code-csharp[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]  

Un finalizador también puede implementarse como una definición de cuerpo de expresión, como se muestra en el ejemplo siguiente.

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 El finalizador llama implícitamente a <xref:System.Object.Finalize%2A> en la clase base del objeto. Por lo tanto, una llamada a un finalizador se convierte implícitamente al siguiente código:  
  
```csharp  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 Esto significa que se realizan llamadas al método `Finalize` de manera recursiva para todas las instancias de la cadena de herencia, desde la más a la menos derivada.  
  
> [!NOTE]
>  Los finalizadores vacíos no deben usarse. Cuando una clase contiene un finalizador, se crea una entrada en la cola `Finalize`. Cuando se llama al finalizador, se invoca al recolector de elementos no utilizados para procesar la cola. Un finalizador vacío simplemente produce una pérdida de rendimiento innecesaria.  
  
 El programador no puede controlar cuándo se llama al finalizador, porque esto lo determina el recolector de elementos no utilizados. El recolector de elementos no utilizados comprueba si hay objetos que ya no están siendo usados por ninguna aplicación. Si considera un objeto elegible para su finalización, llama al finalizador (si existe) y reclama la memoria usada para almacenar el objeto. También se llama a los finalizadores cuando se cierra el programa.  
  
 Es posible forzar la recolección de elementos no utilizados llamando a <xref:System.GC.Collect%2A>, pero en general debe evitarse su uso por razones de rendimiento.  
  
## <a name="using-finalizers-to-release-resources"></a>Usar finalizadores para liberar recursos  
 En general, C# no requiere tanta administración de memoria como se necesita al desarrollar con un lenguaje que no está diseñado para un runtime con recolección de elementos no utilizados. Esto es debido a que el recolector de elementos no utilizados de .NET Framework administra implícitamente la asignación y liberación de memoria para los objetos. En cambio, cuando la aplicación encapsule recursos no administrados como ventanas, archivos y conexiones de red, debería usar finalizadores para liberar dichos recursos. Cuando el objeto cumple los requisitos para su finalización, el recolector de elementos no utilizados ejecuta el método `Finalize` del objeto.  
  
## <a name="explicit-release-of-resources"></a>Liberación explícita de recursos  
 Si la aplicación usa un recurso externo costoso, también es recomendable liberar explícitamente el recurso antes de que el recolector de elementos no utilizados libere el objeto. Para ello debe implementar un método `Dispose` desde la interfaz <xref:System.IDisposable> que realiza la limpieza del objeto necesaria. Esto puede mejorar considerablemente el rendimiento de la aplicación. Aunque controle explícitamente los recursos, el finalizador garantiza la liberación de recursos si la llamada al método `Dispose` genera un error.  
  
 Para obtener más detalles sobre la liberación de recursos, vea los siguientes temas:  
  
-   [Limpieza de recursos no administrados](../../../standard/garbage-collection/unmanaged.md)  
  
-   [Implementación de un método Dispose](../../../standard/garbage-collection/implementing-dispose.md)  
  
-   [using (instrucción)](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se crean tres clases que forman una cadena de herencia. La clase `First` es la clase base, `Second` se deriva de `First` y `Third` se deriva de `Second`. Los tres tienen finalizadores. En `Main`, se crea una instancia de la clase más derivada. Cuando ejecute el programa, observe que se llama a los finalizadores de las tres clases automáticamente y en orden, desde la más derivada hasta la menos derivada.  
  
 [!code-csharp[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IDisposable>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
