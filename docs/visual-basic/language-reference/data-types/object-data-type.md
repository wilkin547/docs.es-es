---
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
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343963"
---
# <a name="object-data-type"></a>Object Data Type

Contiene direcciones que hacen referencia a objetos. Puede asignar cualquier tipo de referencia (cadena, matriz, clase o interfaz) a una variable de `Object`. Una variable `Object` también puede hacer referencia a datos de cualquier tipo de valor (Numeric, `Boolean`, `Char`, `Date`, Structure o Enumeration).

## <a name="remarks"></a>Comentarios

El tipo de datos `Object` puede apuntar a datos de cualquier tipo de datos, incluida cualquier instancia de objeto que la aplicación reconozca. Use `Object` cuando no conozca en tiempo de compilación a qué tipo de datos puede apuntar la variable.

El valor predeterminado de `Object` es `Nothing` (una referencia nula).

## <a name="data-types"></a>Tipos de datos

Puede asignar una variable, una constante o una expresión de cualquier tipo de datos a una variable de `Object`. Para determinar el tipo de datos al que hace referencia una variable `Object` actualmente, puede usar el método <xref:System.Type.GetTypeCode%2A> de la clase <xref:System.Type?displayProperty=nameWithType>. En el ejemplo siguiente se ilustra esto.

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

El tipo de datos `Object` es un tipo de referencia. Sin embargo, Visual Basic trata una variable `Object` como un tipo de valor cuando hace referencia a los datos de un tipo de valor.

## <a name="storage"></a>Almacenamiento

Sea cual sea el tipo de datos al que haga referencia, una variable `Object` no contenga el propio valor de datos, sino un puntero al valor. Siempre usa cuatro bytes en la memoria del equipo, pero no incluye el almacenamiento de los datos que representan el valor de la variable. Debido al código que usa el puntero para ubicar los datos, `Object` variables que contienen tipos de valor son ligeramente más lentas de tener acceso que las variables de tipo explícito.

## <a name="programming-tips"></a>Sugerencias de programación

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos de puntero en otros entornos no son compatibles con el tipo de `Object` Visual Basic.

- **Rendimiento.** Una variable que se declara con el tipo `Object` es lo suficientemente flexible como para contener una referencia a cualquier objeto. Sin embargo, cuando se invoca un método o una propiedad en este tipo de variable, siempre se incurre en el *enlace* en tiempo de ejecución (en tiempo de ejecución). Para forzar el *enlace anticipado* (en tiempo de compilación) y un mejor rendimiento, declare la variable con un nombre de clase específico o conviértala en el tipo de datos específico.

  Al declarar una variable de objeto, intente usar un tipo de clase concreto, por ejemplo <xref:System.OperatingSystem>, en lugar del tipo de `Object` generalizado. También debe utilizar la clase más específica disponible, como <xref:System.Windows.Forms.TextBox> en lugar de <xref:System.Windows.Forms.Control>, de modo que pueda tener acceso a sus propiedades y métodos. Normalmente, puede usar la lista **clases** de la **Examinador de objetos** para buscar los nombres de clase disponibles.

- **Ampliación.** Todos los tipos de datos y todos los tipos de referencia se amplían al tipo de datos `Object`. Esto significa que puede convertir cualquier tipo en `Object` sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.

  Sin embargo, si se convierte entre tipos de valor y `Object`, Visual Basic realiza operaciones denominadas *conversión boxing y conversión* *unboxing*, lo que ralentiza la ejecución.

- **Caracteres de tipo.** `Object` no tiene un carácter de tipo literal o un carácter de tipo de identificador.

- **Tipo de marco.** El tipo correspondiente en el .NET Framework es la clase <xref:System.Object?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra una variable de `Object` que apunta a una instancia de objeto.

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>Vea también

- <xref:System.Object>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Determinar si dos objetos están relacionados](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Determinar si dos objetos son idénticos](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
