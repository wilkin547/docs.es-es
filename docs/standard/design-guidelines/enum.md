---
title: Diseño de enumeraciones
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: KrzysztofCwalina
ms.openlocfilehash: e890ebbbeb04ca424b84c11791e5ce7fa55db72e
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663476"
---
# <a name="enum-design"></a>Diseño de enumeraciones

Las enumeraciones son un tipo especial de tipo de valor. Hay dos tipos de enumeraciones: enumeraciones simples de enumeraciones y marca.

Enumeraciones simples representan conjuntos cerrados pequeño de opciones. Un ejemplo común de la enumeración simple es un conjunto de colores.

Marca enumeraciones están diseñadas para admitir las operaciones bit a bit de los valores de enumeración. Un ejemplo común de la enumeración de marcas es una lista de opciones.

**✓ DO** utilizar una enumeración para establecimiento inflexible de tipos, parámetros, propiedades y valores que representan conjuntos de valores devueltos.

**✓ DO** favorecen el uso de una enumeración en lugar de constantes estáticas.

**X DO NOT** utilizar una enumeración para conjuntos abiertos (por ejemplo, la versión del sistema operativo, los nombres de sus amigos, etcetera).

**X DO NOT** proporcionar valores de enumeración reservado que se han diseñado para un uso futuro.

Simplemente siempre puede agregar valores a la enumeración existente en una etapa posterior. Consulte [agregar valores a enumeraciones](#add_value) para obtener más información sobre cómo agregar valores a las enumeraciones. Los valores de reservado simplemente contaminen el conjunto de valores reales y tienden a producir errores de usuario.

**X AVOID** exponer públicamente las enumeraciones con un único valor.

Es una práctica común para garantizar la futura extensibilidad de C API agregar parámetros reservados para las firmas de método. Estos parámetros reservados pueden expresarse como enumeraciones con un valor predeterminado único. No debe realizarse en las API administradas. Sobrecarga de métodos permite agregar parámetros en futuras versiones.

**X DO NOT** incluir los valores de centinela en las enumeraciones.

Aunque a veces son útiles para los desarrolladores de framework, los valores de centinela son confusos para los usuarios de framework. Se utilizan para realizar un seguimiento del estado de la enumeración en lugar de ser uno de los valores del conjunto representado por la enumeración.

**✓ DO** proporcionar un valor de cero en enumeraciones simples.

Considere la posibilidad de llamar a algo parecido a "None". el valor Si este valor no es adecuado para esta enumeración determinada, el valor predeterminado más común para la enumeración debe asignarse el valor subyacente cero.

**✓ CONSIDER** con <xref:System.Int32> (el valor predeterminado en la mayoría de lenguajes de programación) como el tipo subyacente de una enumeración, a menos que cualquiera de las acciones siguientes es verdadera:

- La enumeración es una enumeración de marcas y dispone de más de 32 indicadores o espera tener más en el futuro.

- El tipo subyacente debe ser diferente de <xref:System.Int32> para facilitar la interoperabilidad con código no administrado espera las enumeraciones de diferente tamaño.

- Un tipo subyacente de menor tamaño daría lugar a importantes ahorros de espacio. Si espera que la enumeración se utiliza principalmente como un argumento para el flujo de control, el tamaño hace poca diferencia. El ahorro de tamaño puede ser considerable si:

  - Esperar la enumeración que se usará como un campo en una estructura con instancias con mucha frecuencia o clase.

  - Se espera que los usuarios para crear matrices de gran tamaño o colecciones de las instancias de la enumeración.

  - Espera un gran número de instancias de la enumeración que se va a serializar.

Para el uso de memoria, tenga en cuenta que los objetos administrados son siempre `DWORD`-alineadas, por lo que necesita de forma eficaz varias enumeraciones u otras estructuras pequeño en una instancia para empaquetar una enumeración con más pequeña para marcar la diferencia, porque el tamaño total de instancias siempre es Si va a redondear hasta un `DWORD`.

**✓ DO** nombre enumeraciones de indicador con nombres plurales o sintagmas nominales y enumeraciones simples con nombres simples o frases.

**X DO NOT** extender <xref:System.Enum?displayProperty=nameWithType> directamente.

<xref:System.Enum?displayProperty=nameWithType> es un tipo especial que CLR usa para crear enumeraciones definidas por el usuario. La mayoría de lenguajes de programación proporcionan un elemento de programación que proporciona acceso a esta funcionalidad. Por ejemplo, en C# el `enum` palabra clave se usa para definir una enumeración.

<a name="design"></a>

### <a name="designing-flag-enums"></a>Diseño de las enumeraciones de marca

**✓ DO** aplicar el <xref:System.FlagsAttribute?displayProperty=nameWithType> para las enumeraciones de indicador. No se aplique este atributo a las enumeraciones simples.

**✓ DO** use potencias de dos para los valores de enumeración de marca para que puedan combinarse libremente utilizando la operación OR bit a bit.

**✓ CONSIDER** proporcionar valores de enumeración especiales para normalmente usa combinaciones de marcas.

Operaciones bit a bit son un concepto avanzado y no debería requerirse para tareas sencillas. <xref:System.IO.FileAccess.ReadWrite> es un ejemplo de este tipo en un valor especial.

**X AVOID** crear enumeraciones de indicador que ciertas combinaciones de valores no son válidos.

**X AVOID** utilizando marca los valores de enumeración de cero a menos que el valor representa "se borran todas las marcas" y se denomina de forma adecuada, según lo prescrito por la instrucción siguiente.

**✓ DO** nombre al valor cero de enumeraciones de marca `None`. Para una enumeración de marca, el valor siempre debe significar "se borran todas las marcas".

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a>Agregar valor a las enumeraciones

Es muy común que detecte que son necesarias agregar valores a una enumeración después de que ya se han enviado. Hay un posible problema de compatibilidad de la aplicación cuando el valor recién agregado se devuelve desde una API existente, porque las aplicaciones mal escritas no podrían controlar correctamente el nuevo valor.

**✓ CONSIDER** agregar valores a las enumeraciones, a pesar de que un pequeño riesgo de compatibilidad.

Si tiene datos reales sobre las incompatibilidades de la aplicación causadas por las adiciones a una enumeración, considere la posibilidad de agregar una nueva API que devuelve los valores nuevos y antiguos y dejar de utilizar la API antigua, que debe continuar devolviendo simplemente los valores anteriores. Esto garantizará que las aplicaciones existentes siguen siendo compatibles.

*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*

*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
