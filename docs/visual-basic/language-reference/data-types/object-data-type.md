---
description: 'Más información acerca de: tipo de datos de objeto'
title: Object Data Type
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: b1f169e4e590335a0879f5ecd9b68507a3fa2ccb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792159"
---
# <a name="object-data-type"></a>Object Data Type

Contiene direcciones que hacen referencia a objetos. Puede asignar cualquier tipo de referencia (cadena, matriz, clase o interfaz) a una `Object` variable. Una `Object` variable también puede hacer referencia a datos de cualquier tipo de valor (Numeric, `Boolean` , `Char` , `Date` , Structure o Enumeration).

## <a name="remarks"></a>Observaciones

El `Object` tipo de datos puede apuntar a datos de cualquier tipo de datos, incluida cualquier instancia de objeto que la aplicación reconozca. Use `Object` cuando no conozca en tiempo de compilación a qué tipo de datos puede apuntar la variable.

El valor predeterminado de `Object` es `Nothing` (una referencia nula).

## <a name="data-types"></a>Tipo de datos

Puede asignar una variable, una constante o una expresión de cualquier tipo de datos a una `Object` variable. Para determinar el tipo de datos `Object` al que hace referencia actualmente una variable, puede utilizar el <xref:System.Type.GetTypeCode%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase. Esto se ilustra en el siguiente ejemplo:

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

El `Object` tipo de datos es un tipo de referencia. Sin embargo, Visual Basic trata una `Object` variable como un tipo de valor cuando hace referencia a los datos de un tipo de valor.

## <a name="storage"></a>Storage

Sea cual sea el tipo de datos al que hace referencia, una `Object` variable no contiene el valor de datos en sí, sino un puntero al valor. Siempre usa cuatro bytes en la memoria del equipo, pero no incluye el almacenamiento de los datos que representan el valor de la variable. Debido al código que usa el puntero para buscar los datos, `Object` las variables que contienen tipos de valor son ligeramente más lentas de tener acceso que las variables de tipo explícito.

## <a name="programming-tips"></a>Sugerencias de programación

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos de puntero en otros entornos no son compatibles con el tipo de Visual Basic `Object` .

- **Rendimiento.** Una variable que se declara con el `Object` tipo es lo suficientemente flexible como para contener una referencia a cualquier objeto. Sin embargo, cuando se invoca un método o una propiedad en este tipo de variable, siempre se incurre en el *enlace* en tiempo de ejecución (en tiempo de ejecución). Para forzar el *enlace anticipado* (en tiempo de compilación) y un mejor rendimiento, declare la variable con un nombre de clase específico o conviértala en el tipo de datos específico.

  Al declarar una variable de objeto, intente usar un tipo de clase concreto, por ejemplo <xref:System.OperatingSystem> , en lugar del tipo generalizado `Object` . También debe usar la clase más específica disponible, como <xref:System.Windows.Forms.TextBox> en lugar de <xref:System.Windows.Forms.Control> , para que pueda tener acceso a sus propiedades y métodos. Normalmente, puede usar la lista **clases** de la **Examinador de objetos** para buscar los nombres de clase disponibles.

- **Ampliación.** Todos los tipos de datos y todos los tipos de referencia se amplían al `Object` tipo de datos. Esto significa que puede convertir cualquier tipo en `Object` sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.

  Sin embargo, si se convierte entre tipos de valor y `Object` , Visual Basic realiza operaciones denominadas *conversión boxing y conversión* *unboxing*, lo que hace que la ejecución sea más lenta.

- **Caracteres de tipo.** `Object` no tiene un carácter de tipo literal o un carácter de tipo de identificador.

- **Tipo de Framework.** El tipo correspondiente en el .NET Framework es la <xref:System.Object?displayProperty=nameWithType> clase.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra una `Object` variable que apunta a una instancia de objeto.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>Vea también

- <xref:System.Object>
- [Tipo de datos](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Procedimiento para determinar si dos objetos están relacionados](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Procedimiento para determinar si dos objetos son idénticos](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
