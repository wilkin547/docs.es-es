---
title: "Destructores (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "~ [C#], en destructores"
  - "lenguaje C#, destructores"
  - "destructores [C#]"
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Destructores (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los destructores se utilizan para destruir instancias de clases.  
  
## Comentarios  
  
-   Los destructores no se pueden definir en structs.  Sólo se utilizan con clases.  
  
-   Una clase sólo puede tener un destructor.  
  
-   Los destructores no se pueden heredar ni sobrecargar.  
  
-   No se puede llamar a los destructores.  Se invocan automáticamente.  
  
-   Un destructor no permite modificadores de acceso ni tiene parámetros.  
  
 Por ejemplo, el siguiente código muestra una declaración de un destructor para la clase `Car`:  
  
 [!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]  
  
 El destructor llama implícitamente al método <xref:System.Object.Finalize%2A> sobre la clase base del objeto.  Por lo tanto, el código de destructor anterior se traduce implícitamente al siguiente código:  
  
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
  
 Esto significa que se realizan llamadas al método `Finalize` de forma recursiva para todas las instancias de la cadena de herencia, desde la más derivada hasta la menos derivada.  
  
> [!NOTE]
>  No se deben utilizar destructores vacíos.  Cuando una clase contiene un destructor, se crea una entrada en la cola `Finalize`.  Cuando se llama al destructor, se invoca al recolector de elementos no utilizados para procesar la cola.  Si el destructor está vacío, simplemente se produce una pérdida de rendimiento innecesaria.  
  
 El programador no puede controlar cuándo se llama al destructor, porque esto lo determina el recolector de elementos no utilizados.  El recolector de elementos no utilizados comprueba si hay objetos que ya no están siendo utilizados por ninguna aplicación.  Si considera un objeto elegible para su destrucción, llama al destructor \(si existe\) y reclama la memoria utilizada para almacenar el objeto.  También se llama a los destructores cuando se cierra el programa.  
  
 Es posible forzar la recolección de elementos no utilizados llamando al método <xref:System.GC.Collect%2A>, pero en general debe evitarse su uso por razones de rendimiento.  
  
## Utilizar destructores para liberar recursos  
 En general, C\# no requiere tanta administración de memoria como se necesita al desarrollar con un lenguaje que no está diseñado para un motor de ejecución con recolección de elementos no utilizados.  Esto es debido a que el recolector de elementos no utilizados de .NET Framework administra implícitamente la asignación y liberación de memoria para los objetos.  Sin embargo, cuando la aplicación encapsule recursos no administrados como ventanas, archivos y conexiones de red, debería utilizar destructores para liberar dichos recursos.  Cuando el objeto cumple los requisitos para su destrucción, el recolector de elementos no utilizados ejecuta el método `Finalize` del objeto.  
  
## Liberación explícita de recursos  
 Si la aplicación utiliza un recurso externo costoso, también es recomendable liberar explícitamente el recurso antes de que el recolector de elementos no utilizados libere el objeto.  Para ello debe implementar un método `Dispose` desde la interfaz <xref:System.IDisposable> que realiza la limpieza del objeto necesaria.  Esto puede mejorar considerablemente el rendimiento de la aplicación.  Aunque controle explícitamente los recursos, el destructor garantiza la liberación de recursos si falla la llamada al método `Dispose`.  
  
 Para obtener más detalles sobre la liberación de recursos, vea los siguientes temas:  
  
-   [Cleaning Up Unmanaged Resources](../Topic/Cleaning%20Up%20Unmanaged%20Resources.md)  
  
-   [Implementing a Dispose Method](../Topic/Implementing%20a%20Dispose%20Method.md)  
  
-   [using \(Instrucción\)](../../../csharp/language-reference/keywords/using-statement.md)  
  
## Ejemplo  
 En el siguiente ejemplo se crean tres clases que forman una cadena de herencia.  La clase `First` es la clase base, `Second` se deriva de `First` y `Third` se deriva de `Second`.  Las tres tienen destructores.  En `Main()`, se crea una instancia de la clase más derivada.  Cuando ejecute el programa, observe que se llama a los destructores de las tres clases automáticamente y en orden, desde la más derivada hasta la menos derivada.  
  
 [!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.IDisposable>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Garbage Collection](../Topic/Garbage%20Collection.md)