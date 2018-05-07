---
title: Diseño de enumeraciones
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 544f617ca3a352814504125d7a61d70db5a81566
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="enum-design"></a>Diseño de enumeraciones
Las enumeraciones son un tipo especial de tipo de valor. Hay dos tipos de enumeraciones: las enumeraciones simples de enumeraciones y marca.  
  
 Las enumeraciones simples representan pequeños conjuntos cerrados de opciones. Un ejemplo común de la enumeración simple es un conjunto de colores.  
  
 Las enumeraciones de indicador están diseñadas para admitir las operaciones bit a bit de los valores de enumeración. Un ejemplo común de la enumeración de marcas es una lista de opciones.  
  
 **✓ HACER** utilizar una enumeración para establecimiento inflexible de tipos, parámetros, propiedades y valores que representan conjuntos de valores devueltos.  
  
 **✓ HACER** favorecen el uso de una enumeración en lugar de constantes estáticas.  
  
 **X DO NOT** utilizar una enumeración para conjuntos abiertos (por ejemplo, la versión del sistema operativo, los nombres de sus amigos, etcetera).  
  
 **X DO NOT** proporcionar valores de enumeración reservado que se han diseñado para un uso futuro.  
  
 Solo puede siempre tiene que agregar valores a la enumeración existente en una fase posterior. Vea [agregar valores a las enumeraciones](#add_value) para obtener más información sobre cómo agregar valores a las enumeraciones. Valores reservados simplemente contamina el conjunto de valores reales y suelen dar lugar a errores de usuario.  
  
 **X evitar** exponer públicamente las enumeraciones con un único valor.  
  
 Es una práctica común para garantizar la extensibilidad futura de API de C agregar parámetros reservados para las firmas de método. Estos parámetros reservados se pueden expresar como enumeraciones con un valor único. No debe realizarse en las API administradas. Sobrecarga de métodos permite agregar parámetros en versiones futuras.  
  
 **X DO NOT** incluir los valores de centinela en las enumeraciones.  
  
 Aunque a veces son útiles para los desarrolladores de framework, los valores de centinela son confusos para los usuarios de framework. Se utilizan para realizar un seguimiento del estado de la enumeración en lugar de ser uno de los valores del conjunto representado por la enumeración.  
  
 **✓ HACER** proporcionar un valor de cero en enumeraciones simples.  
  
 Tenga en cuenta el valor de llamada algo parecido a "Ninguno". Si este valor no es adecuado para esta enumeración determinada, el valor predeterminado más común para la enumeración debe tener asignado el valor subyacente de cero.  
  
 **✓ Considere la posibilidad de** con <xref:System.Int32> (el valor predeterminado en la mayoría de lenguajes de programación) como el tipo subyacente de una enumeración, a menos que cualquiera de las acciones siguientes es verdadera:  
  
-   La enumeración es una enumeración de marcas y dispone de más de 32 indicadores o espera tener más en el futuro.  
  
-   El tipo subyacente debe ser diferente de <xref:System.Int32> para facilitar la interoperabilidad con código no administrado que espera las enumeraciones de tamaño diferente.  
  
-   Un tipo subyacente de menor tamaño daría como resultado un ahorro sustancial en el espacio. Si espera que la enumeración se utiliza principalmente como un argumento para el flujo de control, el tamaño hace poca diferencia. El ahorro de tamaño podría ser importante si:  
  
    -   Se espera que la enumeración que se usará como un campo en una estructura muy a menudo se ha creado una instancia o clase.  
  
    -   Se espera que los usuarios para crear matrices de gran tamaño o colecciones de las instancias de enumeración.  
  
    -   Espera un gran número de instancias de la enumeración que se va a serializar.  
  
 Para el uso de memoria, tenga en cuenta que los objetos administrados son siempre `DWORD`-alineados, por lo que necesita eficazmente varias enumeraciones u otras estructuras pequeños en una instancia para empaquetar una enumeración con menor para marcar la diferencia, porque el tamaño de la instancia total es siempre Si va a redondear hasta un `DWORD`.  
  
 **✓ HACER** nombre enumeraciones de indicador con nombres plurales o sintagmas nominales y enumeraciones simples con nombres simples o frases.  
  
 **X DO NOT** extender <xref:System.Enum?displayProperty=nameWithType> directamente.  
  
 <xref:System.Enum?displayProperty=nameWithType> es un tipo especial que CLR usa para crear enumeraciones definidas por el usuario. La mayoría de lenguajes de programación proporcionan un elemento de programación que proporciona acceso a esta funcionalidad. Por ejemplo, en C# el `enum` palabra clave se utiliza para definir una enumeración.  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a>Diseñar enumeraciones de indicador  
 **✓ HACER** aplicar el <xref:System.FlagsAttribute?displayProperty=nameWithType> para las enumeraciones de indicador. No se aplican este atributo a las enumeraciones simples.  
  
 **✓ HACER** use potencias de dos para los valores de enumeración de marca para que puedan combinarse libremente utilizando la operación OR bit a bit.  
  
 **✓ Considere la posibilidad de** proporcionar valores de enumeración especiales para normalmente usa combinaciones de marcas.  
  
 Operaciones bit a bit son un concepto avanzado y no deberían ser necesarias para tareas sencillas. <xref:System.IO.FileAccess.ReadWrite> es un ejemplo de este tipo de valor especial.  
  
 **X evitar** crear enumeraciones de indicador que ciertas combinaciones de valores no son válidos.  
  
 **X evitar** utilizando marca los valores de enumeración de cero a menos que el valor representa "se borran todas las marcas" y se denomina de forma adecuada, según lo prescrito por la instrucción siguiente.  
  
 **✓ HACER** nombre al valor cero de enumeraciones de marca `None`. Para una enumeración de marca, el valor siempre debe significar "se borran todos los indicadores".  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a>Agregar valor a las enumeraciones  
 Es muy común para detectar que deba agregar valores a una enumeración después de que ya ha enviado. Hay un posible problema de compatibilidad de aplicaciones cuando el valor recién agregado se devuelve desde una API existente, porque las aplicaciones mal escritas no pueden controlar el nuevo valor correctamente.  
  
 **✓ Considere la posibilidad de** agregar valores a las enumeraciones, a pesar de que un pequeño riesgo de compatibilidad.  
  
 Si tiene datos reales sobre incompatibilidades causadas por las adiciones a una enumeración, considere la posibilidad de agregar una nueva API que devuelve los valores antiguos y nuevos y dejar de utilizar la API antigua, que debería devolver solo los valores anteriores. Esto garantizará que las aplicaciones existentes siguen siendo compatibles.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
