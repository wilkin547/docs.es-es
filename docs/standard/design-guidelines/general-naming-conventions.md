---
title: Convenciones generales de nomenclatura
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 207227b3e5c52b7c6e0f704543379874f3708c03
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338109"
---
# <a name="general-naming-conventions"></a>Convenciones generales de nomenclatura
Esta sección describe generales convenciones de nomenclatura que se relacionan con la elección de palabras, directrices sobre el uso de las abreviaturas y acrónimos y recomendaciones sobre cómo evitar el uso de nombres específicos del idioma.  
  
## <a name="word-choice"></a>Elección de palabras  
 **✓ DO** elegir nombres fácilmente legibles para los identificadores.  
  
 Por ejemplo, una propiedad denominada `HorizontalAlignment` es inglés-lee mejor que `AlignmentHorizontal`.  
  
 **✓ DO** preferible la legibilidad a la mayor brevedad.  
  
 El nombre de propiedad `CanScrollHorizontally` es mejor que `ScrollableX` (una referencia oculta al eje x).  
  
 **X DO NOT** usar caracteres de subrayado, guiones o caracteres no alfanuméricos.  
  
 **X DO NOT** utilizar la notación húngara.  
  
 **X AVOID** utilizando identificadores que están en conflicto con las palabras clave de ampliamente utilizar lenguajes de programación.  
  
 Según la regla 4 de Common Language Specification (CLS), todos los lenguajes compatibles con deben proporcionar un mecanismo que permite el acceso a elementos con nombre que utiliza una palabra clave de ese idioma como un identificador. C#, por ejemplo, utiliza el @ inicio de sesión como un mecanismo de escape en este caso. Sin embargo, todavía es una buena idea para evitar palabras clave comunes porque es mucho más difícil de usar un método con la secuencia de escape que uno sin él.  
  
## <a name="using-abbreviations-and-acronyms"></a>Uso de las abreviaturas y acrónimos  
 **X DO NOT** utilice abreviaturas ni contracciones como parte de los nombres de identificador.  
  
 Por ejemplo, utilice `GetWindow` en lugar de `GetWin`.  
  
 **X DO NOT** usar los acrónimos que no son ampliamente aceptada e incluso si son, solo cuando sea necesario.  
  
## <a name="avoiding-language-specific-names"></a>Evitar los nombres específicos del idioma  
 **✓ DO** utilice nombres con interés semántico en lugar de palabras clave específicas del idioma para los nombres de tipo.  
  
 Por ejemplo, `GetLength` es un nombre más adecuado que `GetInt`.  
  
 **✓ DO** utilizar un nombre de tipo genérico de CLR, en lugar de un nombre específico del lenguaje, en los casos poco frecuentes cuando un identificador no tiene ningún significado semántico más allá de su tipo.  
  
 Por ejemplo, un método de conversión a <xref:System.Int64> debe denominarse `ToInt64`, no `ToLong` (porque <xref:System.Int64> es un nombre CLR para C#-alias específico `long`). En la tabla siguiente presenta varios tipos de base de datos con los nombres de tipo CLR (así como los nombres de tipo correspondiente para C#, Visual Basic y C++).  
  
|C#|Visual Basic|C++|CLR|  
|---------|------------------|-----------|---------|  
|**sbyte**|**SByte**|**char**|**SByte**|  
|**byte**|**Byte**|**unsigned char**|**Byte**|  
|**short**|**Short**|**short**|**Int16**|  
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|  
|**int**|**Integer**|**int**|**Int32**|  
|**uint**|**UInt32**|**unsigned int**|**UInt32**|  
|**long**|**Long**|**__int64**|**Int64**|  
|**ulong**|**UInt64**|**unsigned __int64**|**UInt64**|  
|**float**|**Single**|**float**|**Single**|  
|**double**|**Double**|**double**|**Double**|  
|**bool**|**Boolean**|**bool**|**Boolean**|  
|**char**|**Char**|**wchar_t**|**Char**|  
|**string**|**String**|**String**|**String**|  
|**object**|**Objeto**|**Objeto**|**Objeto**|  
  
 **✓ DO** utilizar un nombre común, como `value` o `item`, en lugar de repetir el nombre de tipo, en los casos poco frecuentes cuando un identificador no tiene ningún significado semántico y el tipo del parámetro no es importante.  
  
## <a name="naming-new-versions-of-existing-apis"></a>Nomenclatura de las nuevas versiones de API existentes  
 **✓ DO** usar un nombre similar a la API anterior al crear nuevas versiones de una API existente.  
  
 Esto ayuda a resaltar la relación entre las API.  
  
 **✓ DO** prefiera agregar un sufijo, en lugar de un prefijo para indicar una nueva versión de una API existente.  
  
 Esto ayudará a detección al examinar la documentación, o usar IntelliSense. La versión anterior de la API se organizarán cerca de las nuevas API, dado que la mayoría de los exploradores e IntelliSense mostrar identificadores en orden alfabético.  
  
 **✓ CONSIDER** con un identificador nuevo, pero significativo, en lugar de agregar un prefijo o un sufijo.  
  
 **✓ DO** use un sufijo numérico para indicar una nueva versión de una API existente, especialmente si el nombre de la API existente es el nombre único que tenga sentido (es decir, si es un estándar del sector) y si agregar cualquier significativo sufijo (o cambiar el nombre) no es una aplicación opción de ropriate.  
  
 **X DO NOT** usar "Ex" (u otro similar) sufijo para un identificador distinguir de una versión anterior de la misma API.  
  
 **✓ DO** utilizar el sufijo "64" al introducir las versiones de API que operan en un entero de 64 bits (un entero largo) en lugar de un entero de 32 bits. Solo debe adoptar este enfoque cuando existe la API de 32 bits existente; no lo haga para la nuevas API con solo una versión de 64 bits.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
