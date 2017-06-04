---
title: "Convenciones de may&#250;sculas y min&#250;sculas | Microsoft Docs"
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
  - "mayúsculas y minúsculas Camel nombres [.NET Framework]"
  - "instrucciones de diseño clases biblioteca [.NET Framework], uso de mayúsculas"
  - "Minúsculas Pascal nombres [.NET Framework]"
  - "distinción entre mayúsculas y minúsculas, las convenciones de mayúsculas y minúsculas"
  - "nombres [.NET Framework], uso de mayúsculas"
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Convenciones de may&#250;sculas y min&#250;sculas
Las instrucciones de este capítulo disponer un método sencillo para el uso de caso de que, cuando se aplican de forma coherente, asegúrese de identificadores para los tipos, miembros y parámetros fáciles de leer.  
  
## Reglas de mayúsculas y minúsculas para los identificadores  
 Para diferenciar las palabras en un identificador, poner en mayúsculas la primera letra de cada palabra en el identificador. No utilice caracteres de subrayado para diferenciar las palabras, o, de hecho, en cualquier lugar de identificadores. Hay dos maneras adecuadas para aprovechar los identificadores, dependiendo del uso del identificador:  
  
-   Pascal  
  
-   seguir el estilo Camel  
  
 La convención Pascal, utilizada para todos los identificadores excepto los nombres de parámetro, se pone en mayúsculas el primer carácter de cada palabra \(incluidos los acrónimos a través de dos letras\), como se muestra en los ejemplos siguientes:  
  
 `PropertyDescriptor`   
 `HtmlTag`  
  
 Se realiza un caso especial para los acrónimos de dos letras en la que se escriben dos letras, como se muestra en el siguiente identificador:  
  
 `IOStream`  
  
 La convención de camelCasing utilizada únicamente para los nombres de parámetro en mayúsculas el primer carácter de cada palabra excepto la primera palabra, como se muestra en los ejemplos siguientes. Como también se muestra en el ejemplo, los acrónimos de dos letras que comenzar un identificador con grafía camel están en minúsculas.  
  
 `propertyDescriptor`   
 `ioStream`   
 `htmlTag`  
  
 **✓ hacer** usar Pascal para todos los nombres de miembro, el tipo y el espacio de nombres públicos que consta de varias palabras.  
  
 **✓ hacer** utilice seguir el estilo Camel para los nombres de parámetro.  
  
 En la tabla siguiente describe las reglas de mayúsculas y minúsculas para diferentes tipos de identificadores.  
  
|Identificador|Mayúsculas y minúsculas|Ejemplo|  
|-------------------|-----------------------------|-------------|  
|Espacio de nombres|Pascal|`namespace System.Security { ... }`|  
|Tipo|Pascal|`public class StreamReader { ... }`|  
|Interfaz|Pascal|`public interface IEnumerable { ... }`|  
|Método|Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|Propiedad|Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|Evento|Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|Campo|Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|Valor de enumeración|Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|Parámetro|Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## Uso de mayúsculas para palabras compuestas y términos comunes  
 La mayoría términos compuestos se tratan como palabras individuales para los fines de mayúsculas y minúsculas.  
  
 **X no** poner en mayúsculas cada palabra en las denominadas palabras compuestas con formato cerrado.  
  
 Éstas son palabras compuestas escritas como una sola palabra, como extremo. Con el fin de obtener instrucciones de mayúsculas y minúsculas, tratar una palabra compuesta con formato cerrado como una sola palabra. Use un diccionario actual para determinar si se escribe una palabra compuesta con formato cerrado.  
  
|Pascal|Camel|No|  
|------------|-----------|--------|  
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
  
## Distinción de mayúsculas y minúsculas  
 Los idiomas que se pueden ejecutar en el CLR no tienen que admitir minúsculas, aunque algunos ofrecen. Incluso si el idioma lo admite, otros lenguajes que pueden tener acceso a su marco no. Ninguna de las API que son accesibles desde el exterior, por lo tanto, no puede confiar en caso de por sí solo para distinguir entre los dos nombres en el mismo contexto.  
  
 **X no** supone que todos los lenguajes de programación distinguen entre mayúsculas y minúsculas. No lo son. Los nombres no pueden diferenciarse por sólo por.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)