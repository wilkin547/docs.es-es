---
title: "Destructores (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ~ [C#], in destructors
- C# language, destructors
- destructors [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6940be34b6cc15f006901e6d14d2a38ebb5d012a
ms.lasthandoff: 03/13/2017

---
# <a name="destructors-c-programming-guide"></a>Destructores (Guía de programación de C#)
Los destructores se utilizan para destruir instancias de clases.  
  
## <a name="remarks"></a>Comentarios  
  
-   Los destructores no se pueden definir en structs. Solo se usan con clases.  
  
-   Una clase solo puede tener un destructor.  
  
-   Los destructores no se pueden heredar ni sobrecargar.  
  
-   No se puede llamar a los destructores. Se invocan automáticamente.  
  
-   Un destructor no permite modificadores ni tiene parámetros.  
  
 Por ejemplo, el siguiente código muestra una declaración de un destructor para la clase `Car`:  
  
 [!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]  
  
 El destructor llama implícitamente al método <xref:System.Object.Finalize%2A> en la clase base del objeto. Por lo tanto, el código de destructor anterior se convierte implícitamente al siguiente código:  
  
```  
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
>  No se deben utilizar destructores vacíos. Cuando una clase contiene un destructor, se crea una entrada en la cola `Finalize`. Cuando se llama al destructor, se invoca al recolector de elementos no utilizados para procesar la cola. Si el destructor está vacío, simplemente se produce una pérdida de rendimiento innecesaria.  
  
 El programador no puede controlar cuándo se llama al destructor, porque esto lo determina el recolector de elementos no utilizados. El recolector de elementos no utilizados comprueba si hay objetos que ya no están siendo usados por ninguna aplicación. Si considera un objeto elegible para su destrucción, llama al destructor (si existe) y reclama la memoria usada para almacenar el objeto. También se llama a los destructores cuando se cierra el programa.  
  
 Es posible forzar la recolección de elementos no utilizados llamando a <xref:System.GC.Collect%2A>, pero en general debe evitarse su uso por razones de rendimiento.  
  
## <a name="using-destructors-to-release-resources"></a>Usar destructores para liberar recursos  
 En general, C# no requiere tanta administración de memoria como se necesita al desarrollar con un lenguaje que no está diseñado para un runtime con recolección de elementos no utilizados. Esto es debido a que el recolector de elementos no utilizados de .NET Framework administra implícitamente la asignación y liberación de memoria para los objetos. En cambio, cuando la aplicación encapsule recursos no administrados como ventanas, archivos y conexiones de red, debería usar destructores para liberar dichos recursos. Cuando el objeto cumple los requisitos para su destrucción, el recolector de elementos no utilizados ejecuta el método `Finalize` del objeto.  
  
## <a name="explicit-release-of-resources"></a>Liberación explícita de recursos  
 Si la aplicación usa un recurso externo costoso, también es recomendable liberar explícitamente el recurso antes de que el recolector de elementos no utilizados libere el objeto. Para ello debe implementar un método `Dispose` desde la interfaz <xref:System.IDisposable> que realiza la limpieza del objeto necesaria. Esto puede mejorar considerablemente el rendimiento de la aplicación. Aunque controle explícitamente los recursos, el destructor garantiza la liberación de recursos si la llamada al método `Dispose` genera un error.  
  
 Para obtener más detalles sobre la liberación de recursos, vea los siguientes temas:  
  
-   [Limpieza de recursos no administrados](http://msdn.microsoft.com/library/a17b0066-71c2-4ba4-9822-8e19332fc213)  
  
-   [Implementación de un método Dispose](http://msdn.microsoft.com/library/eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9)  
  
-   [using (instrucción)](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se crean tres clases que forman una cadena de herencia. La clase `First` es la clase base, `Second` se deriva de `First` y `Third` se deriva de `Second`. Las tres tienen destructores. En `Main()`, se crea una instancia de la clase más derivada. Cuando ejecute el programa, observe que se llama a los destructores de las tres clases automáticamente y en orden, desde la más derivada hasta la menos derivada.  
  
 [!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IDisposable>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Recolección de elementos no utilizados](../../../standard/garbagecollection/index.md)
