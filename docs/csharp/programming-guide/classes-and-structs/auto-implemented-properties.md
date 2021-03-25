---
title: 'Propiedades autoimplementadas: Guía de programación de C#'
description: En el caso de una propiedad implementada automáticamente en C#, el compilador crea un campo de respaldo privado y anónimo al que solo se accede a través de los descriptores de acceso get y set de la propiedad.
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: ef3e2d6dd5851801ea06d65b87c2274d8e44b4f1
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190286"
---
# <a name="auto-implemented-properties-c-programming-guide"></a>Propiedades autoimplementadas (Guía de programación de C#)

En C# 3.0 y versiones posteriores, las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa cuando no es necesaria ninguna lógica adicional en los descriptores de acceso de la propiedad. También permite que el código de cliente cree objetos. Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede acceder con los descriptores de acceso de propiedad `get` y `set`. En C# 9 y versiones posteriores, los descriptores de acceso `init` también se pueden declarar como propiedades implementadas automáticamente.
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra una clase simple que tiene algunas propiedades implementadas automáticamente:  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

No se pueden declarar propiedades implementadas automáticamente en interfaces. Las propiedades implementadas automáticamente declaran un campo de respaldo de instancia privada y las interfaces no pueden declarar campos de instancia. Al declarar una propiedad en una interfaz sin definir un cuerpo, se declara una propiedad con descriptores de acceso que debe ser implementada por cada tipo que implemente esa interfaz.

En C# 6 y versiones posteriores, puede inicializar las propiedades implementadas automáticamente de forma similar a los campos:  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

La clase que se muestra en el ejemplo anterior es mutable. El código de cliente puede cambiar los valores de los objetos una vez creados. En clases complejas que contienen el comportamiento importante (métodos) y los datos, suele ser necesario tener propiedades públicas. Pero para las clases pequeñas o estructuras que solo encapsulan un conjunto de valores (datos) y tienen poco o ningún comportamiento, debe usar una de las opciones siguientes para hacer que los objetos sean inmutables:

* Declare solo un descriptor de acceso `get` (inmutable en cualquier lugar excepto el constructor).
* Declare un descriptor de acceso `get` y un descriptor de acceso `init` (inmutable en cualquier lugar excepto durante la construcción del objeto).
* Declare el descriptor de acceso `set` como [private](../../language-reference/keywords/private.md) (inmutable para los consumidores).

Para obtener más información, vea [Procedimiento para implementar una clase ligera con propiedades autoimplementadas](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).

## <a name="see-also"></a>Consulte también

- [Propiedades](./properties.md)
- [Modificadores](../../language-reference/keywords/index.md)
