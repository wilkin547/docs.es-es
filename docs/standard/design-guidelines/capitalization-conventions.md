---
title: Normas referentes al uso de minúsculas y mayúsculas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ef7913a2601c3a791cb028b4074ce37b9e9421b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="capitalization-conventions"></a>Normas referentes al uso de minúsculas y mayúsculas
Las directrices descritas en este capítulo disponer un método sencillo para el uso de mayúsculas, cuando se aplica de forma coherente, asegúrese de identificadores para los tipos, miembros y parámetros fáciles de leer.  
  
## <a name="capitalization-rules-for-identifiers"></a>Reglas de mayúsculas y minúsculas para los identificadores  
 Para diferenciar las palabras en un identificador, poner en mayúscula la primera letra de cada palabra en el identificador. No use caracteres de subrayado para diferenciar las palabras o con este propósito, en cualquier lugar en los identificadores. Hay dos maneras adecuados aprovechar identificadores, según el uso del identificador:  
  
-   Pascal  
  
-   seguir el estilo Camel  
  
 La convención Pascal, utilizada para todos los identificadores excepto los nombres de parámetro, se pone en mayúsculas el primer carácter de cada palabra (incluidos los acrónimos a través de dos letras de longitud), tal como se muestra en los ejemplos siguientes:  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 Se ha realizado un caso especial para los acrónimos de dos letras en el que están en dos letras en mayúscula, como se muestra en el siguiente identificador:  
  
 `IOStream`  
  
 La convención de seguir el estilo Camel, usar solo para los nombres de parámetro, pone en mayúsculas el primer carácter de cada palabra excepto la primera palabra, como se muestra en los ejemplos siguientes. Como también se muestra en el ejemplo, acrónimos de dos letras que comenzar un identificador con grafía camel son en minúsculas.  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 **✓ HACER** usar Pascal para todos los nombres de miembro, el tipo y el espacio de nombres públicos que consta de varias palabras.  
  
 **✓ HACER** utilice seguir el estilo Camel para los nombres de parámetro.  
  
 En la tabla siguiente describe las reglas de mayúsculas y minúsculas para diferentes tipos de identificadores.  
  
|Identificador|Mayúsculas y minúsculas|Ejemplo|  
|----------------|------------|-------------|  
|Espacio de nombres|Pascal|`namespace System.Security { ... }`|  
|Tipo|Pascal|`public class StreamReader { ... }`|  
|Interfaz|Pascal|`public interface IEnumerable { ... }`|  
|Método|Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|Property|Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|evento|Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|Campo|Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|Valor de enumeración|Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|Parámetro|Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a>Poner en mayúsculas palabras compuestas y términos comunes  
 La mayoría de términos compuestos se tratan como palabras individuales para los fines de mayúsculas y minúsculas.  
  
 **X DO NOT** poner en mayúsculas cada palabra en denominadas palabras compuestas con formato cerrado.  
  
 Éstas son palabras compuestas que se escribe como una sola palabra, como punto de conexión. Con el fin de obtener instrucciones de mayúsculas y minúsculas, tratar una palabra compuesta con formato cerrado como una sola palabra. Use un diccionario actual para determinar si se escribe una palabra compuesta en forma cerrada.  
  
|Pascal|Camel|No|  
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
  
## <a name="case-sensitivity"></a>Distinción de mayúsculas y minúsculas  
 Lenguajes que se pueden ejecutar en el CLR no se necesitan para admitir esta característica, aunque algunos no. Incluso si el idioma lo admite, otros lenguajes que pueden tener acceso el marco no lo hace. Ninguna API que esté accesible desde el exterior, por lo tanto, no se puede confiar en el caso de por sí solo para distinguir entre los dos nombres en el mismo contexto.  
  
 **X DO NOT** se supone que todos los lenguajes de programación distinguen entre mayúsculas y minúsculas. pero no lo son. Los nombres no pueden diferenciarse por sólo por sus mayúsculas.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
