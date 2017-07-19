---
title: static (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- static
- static_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: 36c9fd396914f2d958615b9f62666a0d0cc47fc1
ms.contentlocale: es-es
ms.lasthandoff: 05/15/2017

---
# <a name="static-c-reference"></a>static (Referencia de C#)
Use el modificador `static` para declarar un miembro estático, que pertenece al propio tipo en lugar de a un objeto específico. El modificador `static` se puede usar con clases, campos, métodos, propiedades, operadores, eventos y constructores, pero no con indexadores, finalizadores o tipos que no sean clases. Para más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Ejemplo  
 La siguiente clase se declara como `static` y contiene solo métodos `static`:  
  
 [!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 Una declaración de constantes o tipos es implícitamente un miembro estático.  
  
 No se puede hacer referencia a los miembros estáticos mediante una instancia. En su lugar, se hace referencia a ellos a través del nombre de tipo. Por ejemplo, considere la siguiente clase:  
  
 [!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 Para hacer referencia al miembro estático `x`, use el nombre completo, `MyBaseC.MyStruct.x`, a menos que el miembro sea accesible desde el mismo ámbito:  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 Mientras que una instancia de una clase contiene una copia independiente de todos los campos de instancias de la clase, solo existe una copia de cada campo estático.  
  
 No se puede usar [this](../../../csharp/language-reference/keywords/this.md) para hacer referencia a métodos estáticos o descriptores de acceso de propiedades.  
  
 Si la palabra clave `static` se aplica a una clase, todos los miembros de esta última deben ser estáticos.  
  
 Las clases y las clases estáticas pueden tener constructores estáticos. Se llama a los constructores estáticos en algún momento entre el inicio del programa y la creación de una instancia de la clase.  
  
> [!NOTE]
>  La palabra clave `static` tiene usos más limitados que en C++. Para ver una comparación con la palabra clave de C++, vea [Clases de almacenamiento (C++)](https://docs.microsoft.com/cpp/cpp/storage-classes-cpp#static).
  
 Para demostrar cómo funcionan los miembros estáticos, imagine una clase que represente el empleado de una empresa. Supongamos que la clase contiene un método de recuento de empleados y un campo para almacenar el número de empleados. El método y el campo no pertenecen a ninguna instancia de empleado. En su lugar, pertenecen a la clase de la empresa. Por lo tanto, se deben declarar como miembros estáticos de la clase.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se lee el nombre y el identificador de un nuevo empleado, se incrementa en uno el recuento de empleados y se muestra la información del nuevo empleado, así como el nuevo número de empleados. Para que resulte más sencillo, este programa lee el número actual de empleados desde el teclado. En una aplicación real, esta información se debe leer desde un archivo.  
  
 [!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra que, aunque se puede inicializar un campo estático usando otro campo estático que aún no se haya declarado, los resultados serán indefinidos hasta que asigne explícitamente un valor al campo estático.  
  
 [!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Modifiers](../../../csharp/language-reference/keywords/modifiers.md)  (Modificadores [Referencia de C#])  
 [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

