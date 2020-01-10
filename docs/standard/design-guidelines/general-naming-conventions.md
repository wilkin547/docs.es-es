---
title: Convenciones generales de nomenclatura
ms.date: 10/22/2008
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
ms.openlocfilehash: d1b01fac7368ffeceb554c6f12aecb8f8760fa1d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709340"
---
# <a name="general-naming-conventions"></a>Convenciones generales de nomenclatura
En esta sección se describen las convenciones de nomenclatura generales relacionadas con la elección de palabras, las instrucciones sobre el uso de abreviaturas y acrónimos, y recomendaciones sobre cómo evitar el uso de nombres específicos del idioma.  
  
## <a name="word-choice"></a>Elección de palabra  
 **✓ DO** elegir nombres fácilmente legibles para los identificadores.  
  
 Por ejemplo, una propiedad denominada `HorizontalAlignment` es más legible para el inglés que `AlignmentHorizontal`.  
  
 **✓ DO** preferible la legibilidad a la mayor brevedad.  
  
 El nombre de la propiedad `CanScrollHorizontally` es mejor que `ScrollableX` (una referencia oculta al eje X).  
  
 **X DO NOT** usar caracteres de subrayado, guiones o caracteres no alfanuméricos.  
  
 **X DO NOT** utilizar la notación húngara.  
  
 **X AVOID** utilizando identificadores que están en conflicto con las palabras clave de ampliamente utilizar lenguajes de programación.  
  
 Según la regla 4 del Common Language Specification (CLS), todos los lenguajes compatibles deben proporcionar un mecanismo que permita el acceso a los elementos con nombre que utilizan una palabra clave de ese lenguaje como identificador. C#, por ejemplo, usa el signo @ como mecanismo de escape en este caso. Sin embargo, sigue siendo una buena idea evitar palabras clave comunes, ya que es mucho más difícil usar un método con la secuencia de escape que una sin ella.  
  
## <a name="using-abbreviations-and-acronyms"></a>Usar abreviaturas y acrónimos  
 **X DO NOT** utilice abreviaturas ni contracciones como parte de los nombres de identificador.  
  
 Por ejemplo, use `GetWindow` en lugar de `GetWin`.  
  
 **X DO NOT** usar los acrónimos que no son ampliamente aceptada e incluso si son, solo cuando sea necesario.  
  
## <a name="avoiding-language-specific-names"></a>Evitar nombres específicos del idioma  
 **✓ DO** utilice nombres con interés semántico en lugar de palabras clave específicas del idioma para los nombres de tipo.  
  
 Por ejemplo, `GetLength` es un nombre mejor que `GetInt`.  
  
 **✓ DO** utilizar un nombre de tipo genérico de CLR, en lugar de un nombre específico del lenguaje, en los casos poco frecuentes cuando un identificador no tiene ningún significado semántico más allá de su tipo.  
  
 Por ejemplo, un método que se convierte en <xref:System.Int64> debe denominarse `ToInt64`, no `ToLong` (porque <xref:System.Int64> es un nombre CLR C#para el alias específico de `long`). En la tabla siguiente se presentan varios tipos de datos base mediante los nombres de tipo de CLR (así como los C#nombres de tipo correspondientes C++para, Visual Basic y).  
  
|C#|de Visual Basic|C++|CLR|  
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
  
## <a name="naming-new-versions-of-existing-apis"></a>Asignar nombres a las nuevas versiones de las API existentes  
 **✓ DO** usar un nombre similar a la API anterior al crear nuevas versiones de una API existente.  
  
 Esto ayuda a resaltar la relación entre las API.  
  
 **✓ DO** prefiera agregar un sufijo, en lugar de un prefijo para indicar una nueva versión de una API existente.  
  
 Esto ayudará a la detección al examinar la documentación o al usar IntelliSense. La versión anterior de la API se organizará cerca de las nuevas API, porque la mayoría de los exploradores e IntelliSense muestran identificadores en orden alfabético.  
  
 **✓ CONSIDER** con un identificador nuevo, pero significativo, en lugar de agregar un prefijo o un sufijo.  
  
 **✓ DO** use un sufijo numérico para indicar una nueva versión de una API existente, especialmente si el nombre de la API existente es el nombre único que tenga sentido (es decir, si es un estándar del sector) y si agregar cualquier significativo sufijo (o cambiar el nombre) no es una aplicación opción de ropriate.  
  
 **X DO NOT** usar "Ex" (u otro similar) sufijo para un identificador distinguir de una versión anterior de la misma API.  
  
 **✓ DO** utilizar el sufijo "64" al introducir las versiones de API que operan en un entero de 64 bits (un entero largo) en lugar de un entero de 32 bits. Solo tiene que tomar este enfoque cuando existe la API de 32 bits existente; no lo haga para las nuevas API con una versión de 64 bits.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
