---
title: Procedimiento para invalidar el método ToString - Guía de programación de C#
description: Obtenga información sobre cómo invalidar el método ToString en C#. Todas las clases o estructuras heredan Object y obtienen ToString, que devuelve una representación de cadena de ese objeto.
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 65b34b485d4b90173a4c956dd0ebaaa590a0c7c9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865013"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>Procedimiento para invalidar el método ToString (Guía de programación de C#)

Cada clase o struct de C# hereda implícitamente la clase <xref:System.Object>. Por consiguiente, cada objeto de C# obtiene el método <xref:System.Object.ToString%2A>, que devuelve una representación de cadena de ese objeto. Por ejemplo, todas las variables de tipo `int` tienen un método `ToString`, que las habilita para devolver su contenido como cadena:  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 Cuando cree una clase o struct personalizados, debe reemplazar el método <xref:System.Object.ToString%2A> para proporcionar información sobre el tipo al código de cliente.  
  
 Para obtener información sobre cómo usar cadenas de formato y otros tipos de formato personalizado con el método `ToString`, vea [Aplicar formato a tipos](../../../standard/base-types/formatting-types.md).  
  
> [!IMPORTANT]
> Cuando decida qué información va a proporcionar a través de este método, considere si la clase o struct se va a usar alguna vez en código que no sea de confianza. Asegúrese de que no proporciona información que pueda ser aprovechada por código malintencionado.  
  
Para reemplazar el método `ToString` en una clase o struct:
  
1. Declare un método `ToString` con los modificadores y el tipo de valor devuelto siguientes:  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. Implemente el método para que devuelva una cadena.  
  
     En el ejemplo siguiente, se devuelve el nombre de la clase, además de los datos específicos de una instancia concreta de la clase.  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     Se puede probar el método `ToString` tal y como se muestra en el siguiente ejemplo de código:  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IFormattable>
- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Cadenas](../strings/index.md)
- [string](../../language-reference/builtin-types/reference-types.md)
- [override](../../language-reference/keywords/override.md)
- [virtual](../../language-reference/keywords/virtual.md)
- [Aplicación de formato a tipos](../../../standard/base-types/formatting-types.md)
