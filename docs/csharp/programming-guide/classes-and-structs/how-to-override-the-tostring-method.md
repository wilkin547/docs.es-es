---
title: "Cómo: Invalidar el método ToString (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
caps.latest.revision: 21
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
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 2dde281d439a07d7736949294772a57e926eb587
ms.contentlocale: es-es
ms.lasthandoff: 03/24/2017

---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Cómo: Invalidar el método ToString (Guía de programación de C#)
Cada clase o struct de C# hereda implícitamente la clase <xref:System.Object>. Por consiguiente, cada objeto de C# obtiene el método <xref:System.Object.ToString%2A>, que devuelve una representación de cadena de ese objeto. Por ejemplo, todas las variables de tipo `int` tienen un método `ToString`, que las habilita para devolver su contenido como cadena:  
  
 [!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 Cuando cree una clase o struct personalizados, debe reemplazar el método <xref:System.Object.ToString%2A> para proporcionar información sobre el tipo al código de cliente.  
  
 Para obtener información sobre cómo usar cadenas de formato y otros tipos de formato personalizado con el método `ToString`, vea [Aplicar formato a tipos](../../../standard/base-types/formatting-types.md).  
  
> [!IMPORTANT]
>  Cuando decida qué información va a proporcionar a través de este método, considere si la clase o struct se va a usar alguna vez en código que no sea de confianza. Asegúrese de que no proporciona información que pueda ser aprovechada por código malintencionado.  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a>Para reemplazar el método ToString en una clase o struct  
  
1.  Declare un método `ToString` con los modificadores y el tipo de valor devuelto siguientes:  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  Implemente el método para que devuelva una cadena.  
  
     En el ejemplo siguiente, se devuelve el nombre de la clase, además de los datos específicos de una instancia concreta de la clase.  
  
     [!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     Se puede probar el método `ToString` tal y como se muestra en el siguiente ejemplo de código:  
  
     [!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IFormattable>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)   
 [string](../../../csharp/language-reference/keywords/string.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [override](../../../csharp/language-reference/keywords/override.md)   
 [virtual](../../../csharp/language-reference/keywords/virtual.md)   
 [Aplicación de formato a tipos](../../../standard/base-types/formatting-types.md)
