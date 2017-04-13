---
title: "Dise&#241;o de enumeraciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "instrucciones de diseño de tipos, enumeraciones"
  - "enumeraciones simples"
  - "enumeraciones [.NET Framework], instrucciones de diseño"
  - "instrucciones de diseño clases biblioteca [.NET Framework], enumeraciones"
  - "enumeraciones de indicadores"
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Dise&#241;o de enumeraciones
Las enumeraciones son un tipo especial de tipo de valor. Hay dos tipos de enumeraciones: enumeraciones simples de enumeraciones y marca.  
  
 Las enumeraciones simples representan pequeños conjuntos cerrados de opciones. Un ejemplo común de la enumeración simple es un conjunto de colores.  
  
 Enumeraciones de indicador están diseñadas para admitir las operaciones bit a bit de los valores de enumeración. Un ejemplo común de la enumeración de marcas es una lista de opciones.  
  
 **✓ hacer** utilizar una enumeración para fuertemente tipado, parámetros, propiedades y valores devueltos que representan conjuntos de valores.  
  
 **✓ hacer** favorecen el uso de una enumeración en lugar de constantes estáticas.  
  
 **X no** utilizar una enumeración para conjuntos abiertos \(como la versión del sistema operativo, los nombres de sus amigos, etc.\).  
  
 **X no** proporcionar valores de enumeración reservados que están pensados para su uso futuro.  
  
 Simplemente siempre puede agregar valores a la enumeración existente en una etapa posterior. Consulte [Agregar valores a las enumeraciones](#add_value) para obtener más detalles sobre cómo agregar valores a las enumeraciones. Valores reservados simplemente contaminan el conjunto de valores reales y tienden a producir errores de usuario.  
  
 **Evitar X** exponer públicamente las enumeraciones con sólo un valor.  
  
 Es una práctica común para garantizar la futura extensibilidad de API de C agregar parámetros reservados para las firmas de método. Estos parámetros reservados pueden expresarse como enumeraciones con un valor predeterminado único. No debe realizarse en la API administradas. Sobrecarga de métodos permite agregar parámetros en futuras versiones.  
  
 **X no** incluya valores de centinela en las enumeraciones.  
  
 Aunque a veces son útiles para los desarrolladores de framework, los valores de centinela son confusos para los usuarios de framework. Se utilizan para realizar un seguimiento del estado de la enumeración en lugar de ser uno de los valores del conjunto representado por la enumeración.  
  
 **✓ hacer** proporcionar un valor de cero en enumeraciones simples.  
  
 El valor llame a algo parecido a "Ninguno". Si este valor no es adecuado para esta enumeración determinada, el valor predeterminado más común para la enumeración debe asignarse el valor subyacente cero.  
  
 **✓, considere la posibilidad de** mediante <xref:System.Int32> \(el valor predeterminado en la mayoría de lenguajes de programación\) como el tipo subyacente de enum a menos que cualquiera de los siguientes es verdadera:  
  
-   La enumeración es una enumeración de marcas y dispone de más de 32 indicadores o espera tener más en el futuro.  
  
-   El tipo subyacente debe ser diferente de <xref:System.Int32> para facilitar la interoperabilidad con código no administrado que espera las enumeraciones de tamaño diferente.  
  
-   Un tipo subyacente de menor tamaño produciría un significativo ahorro de espacio. Si espera que la enumeración se utiliza principalmente como un argumento para el flujo de control, el tamaño hace poca diferencia. Los ahorros de tamaño podrían ser significativos si:  
  
    -   Espera a que la enumeración que se usará como un campo en una estructura con mucha frecuencia instancia o clase.  
  
    -   Espera que los usuarios creen matrices grandes o colecciones de instancias de enumeración.  
  
    -   Se espera un gran número de instancias de la enumeración que se va a serializar.  
  
 Para el uso de memoria, tenga en cuenta que los objetos administrados son siempre `DWORD`\-alineado, por lo que necesita eficazmente varias enumeraciones u otras estructuras pequeñas en una instancia para empaquetar una enumeración con menor con el fin de marcar la diferencia, porque el tamaño total de instancia siempre se va a redondear hasta un `DWORD`.  
  
 **✓ hacer** nombre enumeraciones de indicador con nombres plurales o sintagmas nominales y enumeraciones simples con singulares sustantivos o sintagmas nominales.  
  
 **X no** extender <xref:System.Enum?displayProperty=fullName> directamente.  
  
 <xref:System.Enum?displayProperty=fullName> es un tipo especial que CLR usa para crear enumeraciones definidas por el usuario. La mayoría de lenguajes de programación proporcionan un elemento de programación que proporciona acceso a esta funcionalidad. Por ejemplo, en C\# la `enum` palabra clave se utiliza para definir una enumeración.  
  
<a name="design"></a>   
### Diseñar enumeraciones de indicador  
 **✓ hacer** aplicar el <xref:System.FlagsAttribute?displayProperty=fullName> para las enumeraciones de indicador. No se aplican este atributo a las enumeraciones simples.  
  
 **✓ hacer** use potencias de dos para los valores de enumeración de marca para que puedan combinarse libremente utilizando la operación OR bit a bit.  
  
 **✓ considere** proporcionar valores de enumeración especiales para normalmente utiliza combinaciones de indicadores.  
  
 Operaciones bit a bit son un concepto avanzado y no debería requerirse para tareas sencillas.<xref:System.IO.FileAccess> es un ejemplo de este tipo de valor especial.  
  
 **Evitar X** crear enumeraciones de indicador donde ciertas combinaciones de valores no son válidos.  
  
 **Evitar X** utilizando marca los valores de enumeración de cero a menos que el valor representa "se borran todos los indicadores" y se denomina correctamente, tal como se indica por la instrucción siguiente.  
  
 **✓ hacer** nombre al valor cero de enumeraciones de indicador `None`. Para una enumeración de marca, el valor siempre debe significar "se borran todos los indicadores".  
  
<a name="add_value"></a>   
### Agregar valor a las enumeraciones  
 Es muy común para detectar que necesite agregar valores a una enumeración cuando ya se han enviado. Hay un posible problema de compatibilidad de aplicaciones cuando se devuelve el valor recién agregado desde una API existente, porque las aplicaciones mal escritas no podrían controlar correctamente el nuevo valor.  
  
 **✓ considere** agregar valores a las enumeraciones a pesar del pequeño riesgo de compatibilidad.  
  
 Si tiene datos reales sobre las incompatibilidades de las aplicaciones causados por las adiciones a una enumeración, considere la posibilidad de agregar una nueva API que devuelve los valores nuevos y antiguos y descartar la API antigua, que debería devolver sólo los valores anteriores. Esto garantiza que las aplicaciones existentes siguen siendo compatibles.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)