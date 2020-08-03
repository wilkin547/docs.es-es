---
title: 'Argumentos opcionales y con nombre: Guía de programación de C#'
description: En C#, los argumentos con nombre especifican argumentos por nombre, no posición. Los argumentos opcionales se pueden omitir.
ms.date: 07/20/2015
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
ms.openlocfilehash: 46b9dc23644e68aea2767f2b990fe7f243a4f357
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864987"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a>Argumentos opcionales y con nombre (Guía de programación de C#)
C# 4 introduce argumentos opcionales y con nombre. Los *argumentos con nombre* permiten especificar un argumento para un parámetro concreto asociando el argumento al nombre del parámetro y no a la posición del parámetro en la lista de parámetros. Los *argumentos opcionales* permiten omitir argumentos para algunos parámetros. Ambas técnicas se pueden usar con métodos, indexadores, constructores y delegados.  
  
 Cuando se usan argumentos opcionales y con nombre, los argumentos se evalúan por el orden en que aparecen en la lista de argumentos, no en la lista de parámetros.  
  
 Los parámetros opcionales y con nombre, cuando se usan conjuntamente, solo permiten especificar argumentos para algunos parámetros de una lista de parámetros opcionales. Esta funcionalidad facilita enormemente las llamadas a interfaces COM, como las API de automatización de Microsoft Office.  
  
## <a name="named-arguments"></a>Argumentos con nombre  
 Los argumentos con nombre le liberan de la necesidad de recordar o buscar el orden de los parámetros de la lista de parámetros de los métodos llamados. El parámetro de cada argumento se puede especificar por nombre de parámetro. Por ejemplo, se puede llamar de la manera habitual a una función que imprime los detalles de un pedido (como por ejemplo, el nombre de vendedor, el nombre de producto y el número del pedido) mediante el envío de argumentos por posición, en el orden definido por la función.
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 Si no recuerda el orden de los parámetros pero conoce sus nombres, puede enviar los argumentos en cualquier orden.  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 Los argumentos con nombre también mejoran la legibilidad del código al identificar lo que cada argumento representa. En el método de ejemplo siguiente, `sellerName` no puede ser nulo ni un espacio en blanco. Como `sellerName` y `productName` son tipos de cadena, en lugar de enviar argumentos por posición, tiene sentido usar argumentos con nombre para eliminar la ambigüedad entre ambos y evitar confusiones para aquellos que lean el código.
  
 Los argumentos con nombre, cuando se usan con argumentos posicionales, son válidos siempre que

- no vayan seguidos de ningún argumento posicional o,

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- _a partir de C# 7.2_, se usen en la posición correcta. En este ejemplo, el parámetro `orderNum` está en la posición correcta pero no se le asigna un nombre de manera explícita.

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 Los argumentos posicionales que siguen a los argumentos con nombre desordenados no son válidos.

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a>Ejemplo  
 Con este código se implementan los ejemplos de esta sección junto con otros adicionales.  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]  
  
## <a name="optional-arguments"></a>Argumentos opcionales  
 La definición de un método, constructor, indexador o delegado puede especificar que sus parámetros son necesarios o que son opcionales. Todas las llamadas deben proporcionar argumentos para todos los parámetros necesarios, pero pueden omitir los argumentos para los parámetros opcionales.  
  
 Cada parámetro opcional tiene un valor predeterminado como parte de su definición. Si no se envía ningún argumento para ese parámetro, se usa el valor predeterminado. Un valor predeterminado debe ser uno de los siguientes tipos de expresiones:  
  
- una expresión constante;  
  
- una expresión con el formato `new ValType()`, donde `ValType` es un tipo de valor, como [enum](../../language-reference/builtin-types/enum.md) o [struct](../../language-reference/builtin-types/struct.md);  
  
- una expresión con el formato [default(ValType)](../../language-reference/operators/default.md), donde `ValType` es un tipo de valor.  
  
 Los parámetros opcionales se definen al final de la lista de parámetros después de los parámetros necesarios. Si el autor de la llamada proporciona un argumento para algún parámetro de una sucesión de parámetros opcionales, debe proporcionar argumentos para todos los parámetros opcionales anteriores. No se admiten espacios separados por comas en la lista de argumentos. Por ejemplo, en el código siguiente, el método de instancia `ExampleMethod` se define con un parámetro necesario y dos opcionales.  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]  
  
 La llamada siguiente a `ExampleMethod` genera un error del compilador, porque se proporciona un argumento para el tercer parámetro pero no para el segundo.  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 Pero si conoce el nombre del tercer parámetro, puede usar un argumento con nombre para realizar la tarea.  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 En IntelliSense los corchetes se usan para indicar parámetros opcionales, como se muestra en la ilustración siguiente:  
  
 ![Captura de pantalla en la que se muestra información rápida de IntelliSense para el método ExampleMethod.](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)  
  
> [!NOTE]
> También puede declarar parámetros opcionales con la clase <xref:System.Runtime.InteropServices.OptionalAttribute> de .NET. Los parámetros `OptionalAttribute` no requieren un valor predeterminado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el constructor de `ExampleClass` tiene un solo parámetro, que es opcional. El método de instancia `ExampleMethod` tiene un parámetro necesario, `required`, y dos parámetros opcionales, `optionalstr` y `optionalint`. El código de `Main` muestra las distintas formas en que se pueden invocar el constructor y el método.  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]  
  
## <a name="com-interfaces"></a>Interfaces COM  
 Los argumentos opcionales y con nombre, además de compatibilidad con objetos dinámicos y otros avances, mejoran considerablemente la interoperabilidad con las API de COM, como las API de automatización de Office.  
  
 Por ejemplo, el método <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> de la interfaz <xref:Microsoft.Office.Interop.Excel.Range> de Microsoft Office Excel tiene siete parámetros, todos ellos opcionales. Estos parámetros se muestran en la ilustración siguiente:  
  
 ![Captura de pantalla en la que se muestra información rápida de IntelliSense para el método AutoFormat.](./media/named-and-optional-arguments/autoformat-method-parameters.png)  
  
 En C# 3.0 y versiones anteriores, se requiere un argumento para cada parámetro, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]  
  
 Pero la llamada a `AutoFormat` se puede simplificar considerablemente mediante argumentos opcionales y con nombre, que se introducen en C# 4.0. Los parámetros opcionales y con nombre permiten omitir el argumento de un parámetro opcional si no se quiere cambiar el valor predeterminado del parámetro. En la siguiente llamada, solo se especifica un valor para uno de los siete parámetros.  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]  
  
 Para obtener más información y ejemplos, vea [Procedimiento para usar argumentos opcionales y con nombre en la programación de Office (Guía de programación de C#)](./how-to-use-named-and-optional-arguments-in-office-programming.md) y [Procedimiento para tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C# (Guía de programación de C#)](../interop/how-to-access-office-onterop-objects.md).  
  
## <a name="overload-resolution"></a>Overload Resolution  
 El uso de argumentos opcionales y con nombre afecta a la resolución de sobrecarga de las maneras siguientes:  
  
- Un método, indexador o constructor es un candidato para la ejecución si cada uno de sus parámetros es opcional o corresponde, por nombre o por posición, a un solo argumento de la instrucción de llamada y el argumento se puede convertir al tipo del parámetro.  
  
- Si se encuentra más de un candidato, se aplican las reglas de resolución de sobrecarga de las conversiones preferidas a los argumentos que se especifican explícitamente. Los argumentos omitidos en parámetros opcionales se ignoran.  
  
- Si dos candidatos se consideran igualmente correctos, la preferencia pasa a un candidato que no tenga parámetros opcionales cuyos argumentos se hayan omitido en la llamada. Se trata de una consecuencia de una preferencia general en la resolución de sobrecarga para los candidatos con menos parámetros.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para usar argumentos opcionales y con nombre en la programación de Office](./how-to-use-named-and-optional-arguments-in-office-programming.md)
- [Uso de tipo dinámico](../types/using-type-dynamic.md)
- [Utilizar constructores](./using-constructors.md)
- [Utilizar indizadores](../indexers/using-indexers.md)
