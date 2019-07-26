---
title: Tipo de datos Object (Visual Basic)
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
ms.openlocfilehash: 1ac906494c49810e3d389591b1044f412e7320bc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513050"
---
# <a name="object-data-type"></a>Object Data Type

Contiene direcciones que hacen referencia a objetos. Puede asignar cualquier tipo de referencia (cadena, matriz, clase o interfaz) a una `Object` variable. Una `Object` variable también puede hacer referencia a datos de cualquier tipo de valor ( `Boolean`Numeric `Char`, `Date`,,, Structure o Enumeration).

## <a name="remarks"></a>Comentarios

El `Object` tipo de datos puede apuntar a datos de cualquier tipo de datos, incluida cualquier instancia de objeto que la aplicación reconozca. Use `Object` cuando no conozca en tiempo de compilación a qué tipo de datos puede apuntar la variable.

El valor predeterminado de `Object` es `Nothing` (una referencia nula).

## <a name="data-types"></a>Tipos de datos

Puede asignar una variable, una constante o una expresión de cualquier tipo de datos a `Object` una variable. Para determinar el tipo de datos `Object` al que hace referencia actualmente una variable, puede <xref:System.Type.GetTypeCode%2A> utilizar el método <xref:System.Type?displayProperty=nameWithType> de la clase. Esto se ilustra en el siguiente ejemplo:

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

El `Object` tipo de datos es un tipo de referencia. Sin embargo, Visual Basic trata `Object` una variable como un tipo de valor cuando hace referencia a los datos de un tipo de valor.

## <a name="storage"></a>Almacenamiento

Sea cual sea el tipo de datos al `Object` que hace referencia, una variable no contiene el valor de datos en sí, sino un puntero al valor. Siempre usa cuatro bytes en la memoria del equipo, pero no incluye el almacenamiento de los datos que representan el valor de la variable. Debido al código que usa el puntero para buscar los datos, `Object` las variables que contienen tipos de valor son ligeramente más lentas de tener acceso que las variables de tipo explícito.

## <a name="programming-tips"></a>Sugerencias de programación

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o com, tenga en cuenta que los tipos de puntero en otros entornos no son `Object` compatibles con el tipo de Visual Basic.

- **Rendimiento.** Una variable que se declara con `Object` el tipo es lo suficientemente flexible como para contener una referencia a cualquier objeto. Sin embargo, cuando se invoca un método o una propiedad en este tipo de variable, siempre se incurre en el *enlace* en tiempo de ejecución (en tiempo de ejecución). Para forzar el *enlace anticipado* (en tiempo de compilación) y un mejor rendimiento, declare la variable con un nombre de clase específico o conviértala en el tipo de datos específico.

  Al declarar una variable de objeto, intente usar un tipo de clase concreto, por ejemplo <xref:System.OperatingSystem>, en lugar del `Object` tipo generalizado. También debe usar la clase más específica disponible, <xref:System.Windows.Forms.TextBox> como en lugar de <xref:System.Windows.Forms.Control>, para que pueda tener acceso a sus propiedades y métodos. Normalmente, puede usar la lista **clases** de la **Examinador de objetos** para buscar los nombres de clase disponibles.

- **Ampliación.** Todos los tipos de datos y todos los tipos de `Object` referencia se amplían al tipo de datos. Esto significa que puede convertir cualquier tipo en `Object` sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.

  Sin embargo, si se convierte entre tipos de `Object`valor y, Visual Basic realiza operaciones denominadas *conversión boxing y conversión* *unboxing*, lo que hace que la ejecución sea más lenta.

- **Caracteres de tipo.** `Object`no tiene un carácter de tipo literal o un carácter de tipo de identificador.

- **Tipo de marco.** El tipo correspondiente en el .NET Framework es la <xref:System.Object?displayProperty=nameWithType> clase.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra `Object` una variable que apunta a una instancia de objeto.

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
- [Cómo: Determinar si dos objetos están relacionados](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Procedimientos: Determinar si dos objetos son idénticos](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
