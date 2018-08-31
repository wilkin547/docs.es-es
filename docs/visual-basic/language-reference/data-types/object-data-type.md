---
title: Tipo de datos de objeto (Visual Basic)
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
ms.openlocfilehash: 94d3ddcf71194eb69a2d26bcdf549aaf693e46e6
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43255711"
---
# <a name="object-data-type"></a>Object Data Type
Contiene las direcciones que hacen referencia a objetos. Puede asignar cualquier tipo de referencia (cadena, matriz, clase o interfaz) a un `Object` variable. Un `Object` variable también puede hacer referencia a los datos de cualquier tipo de valor (numérico, `Boolean`, `Char`, `Date`, estructura o enumeración).  
  
## <a name="remarks"></a>Comentarios  
 El `Object` puede apuntar el tipo de datos a los datos de cualquier tipo de datos, incluidas las instancias de objeto que la aplicación reconozca. Use `Object` la variable de tipo de datos es posible que elija cuando se desconoce en tiempo de compilación.  
  
 El valor predeterminado de `Object` es `Nothing` (una referencia nula).  
  
## <a name="data-types"></a>Tipos de datos  
 Puede asignar una variable, constante o expresión de cualquier tipo de datos para un `Object` variable. Para determinar el tipo de datos un `Object` variable hace referencia actualmente a, puede usar el <xref:System.Type.GetTypeCode%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase. Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 El `Object` tipo de datos es un tipo de referencia. Sin embargo, Visual Basic trata un `Object` variable como un tipo de valor al que hace referencia a los datos de un tipo de valor.  
  
## <a name="storage"></a>Almacenamiento  
 Cualquier tipo de datos, lo que hace referencia un `Object` variable no contiene el valor de datos propio, sino un puntero al valor. Siempre utiliza cuatro bytes en memoria del equipo, pero esto no incluye el almacenamiento para los datos que representa el valor de la variable. Debido al código que usa el puntero para localizar los datos, `Object` las variables que contienen tipos de valor son ligeramente más lentas acceder de forma explícita las variables con tipo.  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Consideraciones de interoperabilidad.** Si interactúa con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, tenga en cuenta que los tipos de puntero en otros entornos no son compatibles con Visual Basic `Object` tipo.  
  
-   **Rendimiento.** Una variable declarada con el `Object` es lo suficientemente flexible como para contener una referencia a cualquier objeto de tipo. Sin embargo, cuando se invoca un método o propiedad en este tipo de variable, se produce siempre *enlace más tarde* (en tiempo de ejecución). Para forzar *enlace anticipado* (en tiempo de compilación) y un mejor rendimiento, declare la variable con un nombre de clase específico o convertirlo al tipo de datos específico.  
  
     Cuando se declara una variable de objeto, intente usar un tipo de clase específica, por ejemplo <xref:System.OperatingSystem>, en lugar de la generalizado `Object` tipo. También se debe utilizar la clase más específica disponible, como <xref:System.Windows.Forms.TextBox> en lugar de <xref:System.Windows.Forms.Control>, de modo que puede tener acceso a sus propiedades y métodos. Normalmente, puede usar el **clases** lista en el **Examinador de objetos** para buscar nombres de clase disponibles.  
  
-   **Ampliación.** Todos los tipos de datos y todos los tipos de referencia se convierten en el `Object` tipo de datos. Esto significa que puede convertir cualquier tipo a `Object` sin que se produzca una <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
     Sin embargo, si convierte entre tipos de valor y `Object`, Visual Basic realiza operaciones llamadas *boxing* y *unboxing*, que ralentizan la ejecución.  
  
-   **Caracteres de tipo.** `Object` no tiene ningún carácter de tipo literal o un carácter de tipo identificador.  
  
-   **Tipo de marco de trabajo.** El tipo correspondiente en .NET Framework es la <xref:System.Object?displayProperty=nameWithType> clase.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se muestra un `Object` variable que señala a una instancia de objeto.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Object>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Determinar si dos objetos están relacionados](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Determinar si dos objetos son idénticos](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
