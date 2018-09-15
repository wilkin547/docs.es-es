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
ms.openlocfilehash: 070fc69728c2cb38e465dab9f6f591a77a857531
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2018
ms.locfileid: "45646735"
---
# <a name="capitalization-conventions"></a>Normas referentes al uso de minúsculas y mayúsculas
Las directrices descritas en este capítulo disponer un método sencillo para el uso de caso de que, cuando se aplica de forma coherente, asegúrese de identificadores para los tipos, miembros y parámetros fáciles de leer.  
  
## <a name="capitalization-rules-for-identifiers"></a>Reglas de mayúsculas y minúsculas para los identificadores  
 Para diferenciar las palabras en un identificador, poner en mayúsculas la primera letra de cada palabra en el identificador. No utilice caracteres de subrayado para diferenciar las palabras, o bien, de hecho, en cualquier lugar en los identificadores. Hay dos maneras adecuados para aprovechar los identificadores, según el uso del identificador:  
  
-   Pascal  
  
-   mayúsculas intercaladas  
  
 La convención Pascal, usada para todos los identificadores, excepto los nombres de parámetro, se pone en mayúsculas el primer carácter de cada palabra (incluidos los acrónimos a través de dos letras de longitud), tal como se muestra en los ejemplos siguientes:  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 Un caso especial se realiza para los acrónimos de dos letras en el que se escriben dos letras, como se muestra en el siguiente identificador:  
  
 `IOStream`  
  
 La convención camelCasing, usa solo para los nombres de parámetro, se pone en mayúsculas el primer carácter de cada palabra, excepto la primera palabra, como se muestra en los ejemplos siguientes. Como también se muestra en el ejemplo, son las siglas de dos letras que comenzar un identificador con grafía camel tanto en minúsculas.  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 **✓ DO** usar Pascal para todos los nombres de miembro, el tipo y el espacio de nombres públicos que consta de varias palabras.  
  
 **✓ DO** utilice seguir el estilo Camel para los nombres de parámetro.  
  
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
  
## <a name="capitalizing-compound-words-and-common-terms"></a>Uso de mayúsculas para las palabras compuestas y términos comunes  
 La mayoría de los términos compuestos se tratan como palabras únicas para los fines de mayúsculas y minúsculas.  
  
 **X DO NOT** poner en mayúsculas cada palabra en denominadas palabras compuestas con formato cerrado.  
  
 Estas son las palabras compuestas que se escribe como una sola palabra, como punto de conexión. Con el fin de las directrices de mayúsculas y minúsculas, tratar una palabra compuesta de formulario cerrado como una sola palabra. Usar un diccionario actual para determinar si se escribe una palabra compuesta en forma cerrada.  
  
|Pascal|Camel|no|  
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
 Los idiomas que se pueden ejecutar en el CLR no tienen que admitir minúsculas, aunque algunos. Incluso si su lenguaje lo admite, otros lenguajes que podrían tener acceso a su marco de trabajo no lo hacen. Ninguna API que es accesible externamente, por lo tanto, no puede confiar en caso de por sí solo para distinguir entre los dos nombres en el mismo contexto.  
  
 **X DO NOT** se supone que todos los lenguajes de programación distinguen entre mayúsculas y minúsculas. pero no lo son. Los nombres no pueden diferenciarse por el caso de por sí solo.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
