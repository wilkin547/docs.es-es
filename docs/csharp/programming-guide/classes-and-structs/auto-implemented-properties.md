---
title: 'Propiedades autoimplementadas: Guía de programación de C#'
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 989266bfc2de9bd5ce2948f09a2b9f19dd2c782e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628298"
---
# <a name="auto-implemented-properties-c-programming-guide"></a>Propiedades autoimplementadas (Guía de programación de C#)

En C# 3.0 y versiones posteriores, las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa cuando no es necesaria ninguna lógica adicional en los descriptores de acceso de la propiedad. También permite que el código de cliente cree objetos. Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede acceder con los descriptores de acceso de propiedad `get` y `set`.
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra una clase simple que tiene algunas propiedades implementadas automáticamente:  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

No se pueden declarar propiedades implementadas automáticamente en interfaces. Las propiedades implementadas automáticamente declaran un campo de respaldo de instancia privada y las interfaces no pueden declarar campos de instancia. Al declarar una propiedad en una interfaz sin definir un cuerpo, se declara una propiedad con descriptores de acceso que debe ser implementada por cada tipo que implemente esa interfaz.

En C# 6 y versiones posteriores, puede inicializar las propiedades implementadas automáticamente de forma similar a los campos:  
 
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
 
La clase que se muestra en el ejemplo anterior es mutable. El código de cliente puede cambiar los valores de los objetos una vez creados. En clases complejas que contienen el comportamiento importante (métodos) y los datos, suele ser necesario tener propiedades públicas. Pero para clases pequeñas o structs que simplemente encapsulan un conjunto de valores (datos) y tienen pocos comportamientos o ninguno, debe establecer que los objetos sean inmutables ya sea declarando el descriptor de acceso set como [private](../../language-reference/keywords/private.md) (inmutable para los consumidores) o declarando solo un descriptor de acceso get (inmutable siempre excepto en el constructor).  Para obtener más información, vea [Procedimiento para implementar una clase ligera con propiedades autoimplementadas](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).

## <a name="see-also"></a>Vea también

- [Propiedades](./properties.md)
- [Modificadores](/dotnet/csharp/language-reference/keywords)
