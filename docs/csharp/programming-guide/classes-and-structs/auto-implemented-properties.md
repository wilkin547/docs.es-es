---
title: 'Propiedades autoimplementadas: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 1277e0908b42b6f8185219a33c2b28537c8b6607
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244198"
---
# <a name="auto-implemented-properties-c-programming-guide"></a>Propiedades autoimplementadas (Guía de programación de C#)
En C# 3.0 y versiones posteriores, las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa cuando no es necesaria ninguna lógica adicional en los descriptores de acceso de la propiedad. También permite que el código de cliente cree objetos. Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede acceder con los descriptores de acceso de propiedad `get` y `set`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una clase simple que tiene algunas propiedades implementadas automáticamente:  
  
 [!code-csharp[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 En C# 6 y versiones posteriores, puede inicializar las propiedades implementadas automáticamente de forma similar a los campos:  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 La clase que se muestra en el ejemplo anterior es mutable. El código de cliente puede cambiar los valores de los objetos una vez creados. En clases complejas que contienen el comportamiento importante (métodos) y los datos, suele ser necesario tener propiedades públicas. Pero para clases pequeñas o structs que simplemente encapsulan un conjunto de valores (datos) y tienen pocos comportamientos o ninguno, debe establecer que los objetos sean inmutables ya sea declarando el descriptor de acceso set como [private](../../../csharp/language-reference/keywords/private.md) (inmutable para los consumidores) o declarando solo un descriptor de acceso get (inmutable siempre excepto en el constructor).  Para obtener más información, vea [Cómo: Implementar una clase ligera con propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).  
  
 Los atributos se permiten en propiedades implementadas automáticamente, pero obviamente no en los campos de respaldo, ya que no se puede acceder a ellos desde el código fuente. Si necesita usar un atributo en el campo de respaldo de una propiedad, cree una propiedad normal.  
  
## <a name="see-also"></a>Vea también

- [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)
