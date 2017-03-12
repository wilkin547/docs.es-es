---
title: "using (Directiva, Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "using (directiva) [C#]"
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# using (Directiva, Referencia de C#)
La directiva `using` tiene tres usos:  
  
-   Para permitir el uso de tipos en un espacio de nombres de manera que no tenga que calificar el uso de un tipo en dicho espacio de nombres:  
  
    ```c#  
    using System.Text;  
    ```  
  
-   Para permitirle acceder a los miembros estáticos de un tipo sin tener que calificar el acceso con el nombre del tipo:  
  
    ```c#  
    using static System.Math;  
    ```  
  
-   Para crear un alias para un espacio de nombre o un tipo.  Esto se denomina una *directiva de alias using*.  
  
    ```c#  
    using Project = PC.MyCompany.Project;  
    ```  
  
 La palabra clave `using` también se usa para crear *instrucciones using*, que ayudan a garantizar que los objetos <xref:System.IDisposable>, como archivos y tipos de letra, se tratan correctamente.  Para obtener más información, vea [Instrucción using](../../../csharp/language-reference/keywords/using-statement.md).  
  
## Usar el tipo estático  
 Puede acceder a los miembros estáticos de un tipo sin tener que calificar el acceso con el nombre del tipo:  
  
```c#  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
  
```  
  
 `Using static` importa solo los miembros estáticos accesibles y los tipos anidados declarados en el tipo especificado.  Los miembros heredados no se importan.  Puede importar desde cualquier tipo con nombre con una directiva estática using, incluidos los módulos de Visual Basic.  Las funciones de nivel superior F\# pueden importarse si aparecen en los metadatos como miembros estáticos de un tipo con nombre cuyo nombre es un identificador de C\# válido, pueden importarse.  
  
 `Using static` habilita los métodos de extensión declarados en el tipo especificado estén para la búsqueda de métodos de extensión.  Pero los nombres de los métodos de extensión no se importan en el ámbito de referencia sin calificar del código.  
  
 Los métodos con el mismo nombre importados desde tipos distintos con directivas estáticas using diferentes en la misma unidad de compilación o espacio de nombres forman un grupo de métodos.  La resolución de sobrecarga dentro de estos grupos de método sigue reglas normales de C\#.  
  
## Comentarios  
 El ámbito de una directiva `using` se limita al archivo en el que aparece.  
  
 Cree un alias `using` para facilitar la calificación de un identificador como espacio de nombres o tipo.  El lado derecho de una directiva de alias using siempre debe ser un tipo completo independientemente de las directivas using que lo precedan.  
  
 Cree una directiva `using` para usar los tipos de un espacio de nombres sin tener que especificarlo.  Una directiva `using` no proporciona acceso a los espacios de nombres que están anidados en el espacio de nombres especificado.  
  
 Los espacios de nombres se dividen en dos categorías: definidos por el sistema y definidos por el usuario.  Los espacios de nombres definidos por el usuario son espacios de nombres definidos en el código.  Para obtener una lista de los espacios de nombres definidos por el sistema, vea [Biblioteca de clases de .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195).  
  
 Para obtener ejemplos de cómo hacer referencia a métodos en otros ensamblados, vea [Crear y usar archivos DLL de C\#](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Ejemplo 1  
  
### Descripción  
 En el ejemplo siguiente se muestra cómo definir y usar un alias `using` para un espacio de nombres:  
  
### Código  
 [!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/csharp/using-directive_1.cs)]  
  
### Comentarios  
 Una directiva de alias using no puede tener un tipo genérico abierto en el lado derecho.  Por ejemplo, no puede crear un alias using para List\<T\>, pero puede crear uno para List\<int\>.  
  
## Ejemplo 2  
  
### Descripción  
 En el ejemplo siguiente se muestra cómo definir una directiva `using` y un alias `using` para una clase:  
  
### Código  
 [!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/csharp/using-directive_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)   
 [using \(Instrucción\)](../../../csharp/language-reference/keywords/using-statement.md)