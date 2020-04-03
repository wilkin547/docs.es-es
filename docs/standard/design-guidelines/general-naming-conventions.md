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
ms.openlocfilehash: ef4a8f571a67477739bbc59d3103ba78dea47177
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635918"
---
# <a name="general-naming-conventions"></a>Convenciones generales de nomenclatura

En esta sección se describen las convenciones de nomenclatura generales relacionadas con la elección de palabras, las directrices sobre el uso de abreviaturas y acrónimos y recomendaciones sobre cómo evitar el uso de nombres específicos del idioma.

## <a name="word-choice"></a>Elección de palabras
 ✔️ elegir nombres de identificador fácilmente legibles.

 Por ejemplo, una `HorizontalAlignment` propiedad denominada es `AlignmentHorizontal`más legible en inglés que .

 ✔️ favorezca la legibilidad sobre la brevedad.

 El nombre `CanScrollHorizontally` de `ScrollableX` la propiedad es mejor que (una referencia oscura al eje X).

 ❌NO utilice guiones bajos, guiones ni ningún otro carácter no alfanumérico.

 ❌NO utilice notación húngara.

 ❌EVITAR el uso de identificadores que entren en conflicto con palabras clave de lenguajes de programación ampliamente utilizados.

 De acuerdo con la regla 4 de la Especificación de lenguaje común (CLS), todos los lenguajes compatibles deben proporcionar un mecanismo que permita el acceso a los elementos con nombre que utilizan una palabra clave de ese idioma como identificador. En este caso, c-, utiliza el signo de la tecla . Sin embargo, sigue siendo una buena idea evitar palabras clave comunes porque es mucho más difícil utilizar un método con la secuencia de escape que uno sin él.

## <a name="using-abbreviations-and-acronyms"></a>Uso de abreviaturas y acrónimos
 ❌NO utilice abreviaturas ni contracciones como parte de los nombres de identificador.

 Por ejemplo, `GetWindow` use `GetWin`en lugar de .

 ❌NO utilice siglas que no sean ampliamente aceptadas, e incluso si lo son, solo cuando sea necesario.

## <a name="avoiding-language-specific-names"></a>Evitar nombres específicos del idioma
 ✔️, utilice nombres semánticamente interesantes en lugar de palabras clave específicas del idioma para los nombres de tipo.

 Por ejemplo, `GetLength` es un `GetInt`nombre mejor que .

 ✔️ DO usan un nombre de tipo CLR genérico, en lugar de un nombre específico del idioma, en los raros casos en que un identificador no tiene ningún significado semántico más allá de su tipo.

 Por ejemplo, un método <xref:System.Int64> que `ToInt64`se `ToLong` convierte <xref:System.Int64> en debe tener el nombre , `long`no (porque es un nombre CLR para el alias específico de C ). En la tabla siguiente se presentan varios tipos de datos base mediante los nombres de tipo CLR (así como los nombres de tipo correspondientes para C, Visual Basic y C++).

|C#|Visual Basic|C++|CLR|
|---------|------------------|-----------|---------|
|**sbyte**|**SByte**|**char**|**SByte**|
|**byte**|**Byte**|**unsigned char**|**Byte**|
|**short**|**Corto**|**short**|**Int16**|
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|
|**int**|**Entero**|**int**|**Int32**|
|**uint**|**UInt32**|**unsigned int**|**UInt32**|
|**Largo**|**long**|**__int64**|**Int64**|
|**ulong**|**UInt64**|**unsigned __int64**|**UInt64**|
|**FLOAT**|**Single**|**FLOAT**|**Single**|
|**double**|**Double**|**double**|**Double**|
|**bool**|**Boolean**|**bool**|**Boolean**|
|**char**|**Char**|**wchar_t**|**Char**|
|**string**|**String**|**String**|**String**|
|**Objeto**|**Object**|**Object**|**Object**|

 ✔️ DO usan un nombre `value` `item`común, como o , en lugar de repetir el nombre de tipo, en los raros casos en que un identificador no tiene ningún significado semántico y el tipo del parámetro no es importante.

## <a name="naming-new-versions-of-existing-apis"></a>Nombrar nuevas versiones de API existentes
 ✔️ usar un nombre similar a la API anterior al crear nuevas versiones de una API existente.

 Esto ayuda a resaltar la relación entre las API.

 ✔️ DO prefiere agregar un sufijo en lugar de un prefijo para indicar una nueva versión de una API existente.

 Esto ayudará a la detección al examinar la documentación o al usar IntelliSense. La versión anterior de la API se organizará cerca de las nuevas API, ya que la mayoría de los exploradores e IntelliSense muestran identificadores en orden alfabético.

 ✔️ CONSIDERA usando un identificador nuevo, pero significativo, en lugar de agregar un sufijo o un prefijo.

 ✔️ utilizar un sufijo numérico para indicar una nueva versión de una API existente, especialmente si el nombre existente de la API es el único nombre que tiene sentido (es decir, si es un estándar del sector) y si agregar cualquier sufijo significativo (o cambiar el nombre) no es una opción adecuada.

 ❌NO utilice el sufijo "Ex" (o similar) de un identificador para distinguirlo de una versión anterior de la misma API.

 ✔️ DO utilizan el sufijo "64" al introducir versiones de API que funcionan en un entero de 64 bits (un entero largo) en lugar de un entero de 32 bits. Solo necesita adoptar este enfoque cuando existe la API de 32 bits existente; no lo hagas para nuevas API con solo una versión de 64 bits.

 *Partes &copy; 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Directrices de diseño del marco](../../../docs/standard/design-guidelines/index.md)
- [Pautas de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
- [Convenciones de nomenclatura de .NET para EditorConfig](/visualstudio/ide/editorconfig-naming-conventions)
