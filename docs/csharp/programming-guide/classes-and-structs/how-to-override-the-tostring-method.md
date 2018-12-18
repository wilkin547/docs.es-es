---
title: 'Procedimiento Invalidar el método ToString: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 0be35b64e9df3ec2a78c62735b1b7072e092f073
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240745"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Procedimiento Invalidar el método ToString (Guía de programación de C#)
Cada clase o struct de C# hereda implícitamente la clase <xref:System.Object>. Por consiguiente, cada objeto de C# obtiene el método <xref:System.Object.ToString%2A>, que devuelve una representación de cadena de ese objeto. Por ejemplo, todas las variables de tipo `int` tienen un método `ToString`, que las habilita para devolver su contenido como cadena:  
  
 [!code-csharp[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
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
  
     [!code-csharp[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     Se puede probar el método `ToString` tal y como se muestra en el siguiente ejemplo de código:  
  
     [!code-csharp[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IFormattable>  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Cadenas](../../../csharp/programming-guide/strings/index.md)  
- [string](../../../csharp/language-reference/keywords/string.md)  
- [new](../../../csharp/language-reference/keywords/new.md)  
- [override](../../../csharp/language-reference/keywords/override.md)  
- [virtual](../../../csharp/language-reference/keywords/virtual.md)  
- [Aplicación de formato a tipos](../../../standard/base-types/formatting-types.md)
