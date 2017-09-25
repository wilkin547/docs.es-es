---
title: using (Directiva, Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1129efd8a1c4058a9648eab61f98cdcef7e9f2f7
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="using-directive-c-reference"></a>using (Directiva, Referencia de C#)
La directiva `using` tiene tres usos:  
  
-   Permitir el uso de tipos en un espacio de nombres de manera que no tenga que calificar el uso de un tipo en dicho espacio de nombres:  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   Permitirle acceder a los miembros estáticos de un tipo sin tener que calificar el acceso con el nombre del tipo. 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    Para obtener más información, vea [using static (Directiva)](using-static.md).

-   Para crear un alias para un espacio de nombre o un tipo. Esto se conoce como *alias using (Directiva)*.  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 La palabra clave `using` también se usa para crear *instrucciones using*, que ayudan a garantizar que los objetos <xref:System.IDisposable>, como archivos y fuentes, se tratan correctamente. Consulte [using (Instrucción)](../../../csharp/language-reference/keywords/using-statement.md) para obtener más información.  
  
## <a name="using-static-type"></a>Usar el tipo estático  
 Puede acceder a los miembros estáticos de un tipo sin tener que calificar el acceso con el nombre del tipo:  
  
```csharp  
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
  
## <a name="remarks"></a>Comentarios  
 El ámbito de una directiva `using` se limita al archivo en el que aparece.  
  
 Cree un alias `using` para facilitar la calificación de un identificador como espacio de nombres o tipo. El lado derecho de una directiva de alias using siempre debe ser un tipo completo independientemente de las directivas using que lo precedan.  
  
 Cree una directiva `using` para usar los tipos de un espacio de nombres sin tener que especificarlo. Una directiva `using` no proporciona acceso a los espacios de nombres que están anidados en el espacio de nombres especificado.  
  
 Los espacios de nombres se dividen en dos categorías: definidos por el sistema y definidos por el usuario. Los espacios de nombres definidos por el usuario son espacios de nombres definidos en el código. Para obtener una lista de los espacios de nombres definidos por el sistema, vea [Biblioteca de clases .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195).  
  
 Para obtener ejemplos de cómo hacer referencia a métodos en otros ensamblados, vea [Crear y usar archivos DLL de C#](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).  
  
## <a name="example-1"></a>Ejemplo 1  
  
 En el ejemplo siguiente se muestra cómo definir y usar un alias `using` para un espacio de nombres:  
  
 [!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 Una directiva de alias using no puede tener un tipo genérico abierto en el lado derecho. Por ejemplo, no puede crear un alias using para List\<T>, pero puede crear uno para List\<int>.  
  
## <a name="example-2"></a>Ejemplo 2  
  
 En el ejemplo siguiente se muestra cómo definir una directiva `using` y un alias `using` para una clase:  
  
 [!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md)  (Usar espacios de nombres)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)  (Espacios de nombres)  
 [using (instrucción)](../../../csharp/language-reference/keywords/using-statement.md)

