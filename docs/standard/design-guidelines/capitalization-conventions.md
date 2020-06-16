---
title: Normas referentes al uso de minúsculas y mayúsculas
description: Aplicar convenciones de mayúsculas y minúsculas para los identificadores, las palabras compuestas y los términos comunes. Comprenda cómo funciona la distinción de mayúsculas y minúsculas en .NET.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 4903dc587d84ef36bfaa641cfbda59484266c23c
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767798"
---
# <a name="capitalization-conventions"></a>Normas referentes al uso de minúsculas y mayúsculas
En las instrucciones de este capítulo se diseña un método sencillo para usar el caso que, cuando se aplica de forma coherente, facilitan la lectura de los identificadores de tipos, miembros y parámetros.

## <a name="capitalization-rules-for-identifiers"></a>Reglas de mayúsculas y minúsculas para identificadores
 Para diferenciar las palabras en un identificador, ponga en mayúscula la primera letra de cada palabra en el identificador. No utilice guiones bajos para diferenciar palabras o, en ese caso, en cualquier parte de los identificadores. Hay dos formas adecuadas de poner en mayúsculas los identificadores, dependiendo del uso del identificador:

- PascalCasing

- Alterne

 La Convención PascalCasing, que se usa para todos los identificadores excepto los nombres de parámetro, pone en mayúsculas el primer carácter de cada palabra (incluidos los acrónimos de dos letras de longitud), como se muestra en los ejemplos siguientes:

 `PropertyDescriptor`
 `HtmlTag`

 Se crea un caso especial para los acrónimos de dos letras en los que ambas letras están en mayúsculas, como se muestra en el siguiente identificador:

 `IOStream`

 La Convención alterne, que solo se usa para nombres de parámetro, pone en mayúsculas el primer carácter de cada palabra excepto la primera palabra, como se muestra en los ejemplos siguientes. Como también se muestra en el ejemplo, los acrónimos de dos letras que comienzan un identificador con grafía Camel están en minúsculas.

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 ✔️ usar PascalCasing para todos los nombres de miembros públicos, tipos y espacios de nombres que se componen de varias palabras.

 ✔️ usar alterne para los nombres de parámetro.

 En la tabla siguiente se describen las reglas de mayúsculas y minúsculas para los distintos tipos de identificadores.

|Identificador|Uso de mayúsculas y minúsculas|Ejemplo|
|----------------|------------|-------------|
|Espacio de nombres|Nomenclatura|`namespace System.Security { ... }`|
|Tipo|Nomenclatura|`public class StreamReader { ... }`|
|Interfaz|Nomenclatura|`public interface IEnumerable { ... }`|
|Método|Nomenclatura|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|Propiedad|Nomenclatura|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|Evento|Nomenclatura|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|Campo|Nomenclatura|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|Valor de enumeración|Nomenclatura|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|Parámetro|camelcase|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a>Poner en mayúsculas palabras compuestas y términos comunes
 La mayoría de los términos compuestos se tratan como palabras únicas para el uso de mayúsculas.

 ❌No ponga en mayúsculas cada palabra en lo que se denomina palabras compuestas de formato cerrado.

 Se trata de palabras compuestas escritas como una sola palabra, como el punto de conexión. En lo que respecta a las directrices de mayúsculas y minúsculas, trate una palabra compuesta de formato cerrado como una sola palabra. Use un diccionario actual para determinar si una palabra compuesta está escrita en formato cerrado.

|Nomenclatura|camelcase|Not|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a>Distinción entre mayúsculas y minúsculas
 No es necesario que los lenguajes que se pueden ejecutar en CLR admitan la distinción de mayúsculas y minúsculas, aunque algunos sí lo hacen. Aunque su lenguaje lo admita, otros lenguajes que puedan tener acceso a su marco de trabajo no lo admiten. Por lo tanto, las API a las que se puede tener acceso externamente no pueden basarse solo en mayúsculas y minúsculas para distinguir entre dos nombres en el mismo contexto.

 ❌NO asuma que todos los lenguajes de programación distinguen mayúsculas de minúsculas. pero no lo son. Los nombres no pueden diferir solo en mayúsculas y minúsculas.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de nomenclatura](naming-guidelines.md)
