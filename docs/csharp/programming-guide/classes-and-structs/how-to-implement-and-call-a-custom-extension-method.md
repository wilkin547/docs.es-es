---
title: "Cómo: Implementar e invocar un método de extensión personalizado (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 15
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
ms.openlocfilehash: 8c1c26640c550ce2b16ffafd59430e92189764f9
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Cómo: Implementar e invocar un método de extensión personalizado (Guía de programación de C#)
En este tema se muestra cómo implementar sus propios métodos de extensión para cualquier tipo de la [biblioteca de clases .NET Framework](http://go.microsoft.com/fwlink/?LinkID=217856) o para cualquier otro tipo .NET que desee extender. El código de cliente puede usar los métodos de extensión agregando una referencia a la DLL que los contiene y agregando una directiva [using](../../../csharp/language-reference/keywords/using-directive.md) que especifique el espacio de nombres en el que se definen los métodos de extensión.  
  
## <a name="to-define-and-call-the-extension-method"></a>Para definir y llamar al método de extensión  
  
1.  Defina una [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) estática que contenga el método de extensión.  
  
     La clase debe estar visible para el código de cliente. Para obtener más información sobre las reglas de accesibilidad, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
2.  Implemente el método de extensión como un método estático con al menos la misma visibilidad que la clase contenedora.  
  
3.  El primer parámetro del método especifica el tipo en el que opera el método; debe ir precedido del modificador [this](../../../csharp/language-reference/keywords/this.md).  
  
4.  En el código de llamada, agregue una directiva `using` para especificar el [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md) que contiene la clase del método de extensión.  
  
5.  Llame a los métodos como si fueran métodos de instancia del tipo.  
  
     Tenga en cuenta que el primer parámetro no se especifica mediante el código de llamada, ya que representa el tipo al que se aplica el operador y el compilador ya conoce el tipo del objeto. Solo tiene que proporcionar argumentos para los parámetros comprendidos entre el 2 y `n`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se implementa un método de extensión denominado `WordCount` en la clase `CustomExtensions.StringExtension`. El método opera en la clase <xref:System.String>, que se especifica como el primer parámetro de método. El espacio de nombres `CustomExtensions` se importa en el espacio de nombres de la aplicación y se llama al método dentro del método `Main`.  
  
 [!code-cs[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este código, cópielo y péguelo en un proyecto de aplicación de la consola de Visual C# creado en [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]. De forma predeterminada, este proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y tiene una referencia a System.Core.dll y una directiva `using` para System.Linq. Si faltan uno o varios de estos requisitos del proyecto, se pueden agregar manualmente.   
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Los métodos de extensión no presentan ninguna vulnerabilidad de seguridad específica. No se pueden usar nunca para suplantar los métodos existentes en un tipo, porque todos los conflictos de nombres se resuelven a favor de la instancia o del método estático definido por el tipo en cuestión. Los métodos de extensión no pueden tener acceso a los datos privados de la clase extendida.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)   
 [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [this](../../../csharp/language-reference/keywords/this.md)   
 [namespace](../../../csharp/language-reference/keywords/namespace.md)

