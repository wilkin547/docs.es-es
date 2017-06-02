---
title: "Convenciones generales de nomenclatura | Microsoft Docs"
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
  - "nombres [.NET Framework], conflictos"
  - "nombres de tipo de conflictos"
  - "nombres de tipo específicos de idioma"
  - "nombres [.NET Framework], acerca de las directrices de nomenclatura"
  - "abreviaturas de los nombres [.NET Framework]"
  - "instrucciones de nomenclatura de abreviatura"
  - "instrucciones de acrónimos de nomenclatura"
  - "Notación húngara"
  - "nombres [.NET Framework], nombres de tipo"
  - "nombres [.NET Framework], acrónimos"
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Convenciones generales de nomenclatura
Esta sección describe las convenciones generales de nomenclatura relacionadas con la elección de palabras, instrucciones de uso de las abreviaturas y acrónimos y recomendaciones acerca de cómo evitar el uso de nombres específicos de idioma.  
  
## Elección de palabras  
 **✓ hacer** elegir nombres de identificador fácilmente legible.  
  
 Por ejemplo, una propiedad denominada `HorizontalAlignment` es inglés\-lee mejor que `AlignmentHorizontal`.  
  
 **✓ hacer** preferible la legibilidad a la brevedad.  
  
 El nombre de propiedad `CanScrollHorizontally` es mejor que `ScrollableX` \(una referencia oculta al eje x\).  
  
 **X no** usar caracteres de subrayado, guiones o caracteres no alfanuméricos.  
  
 **X no** utilizar la notación húngara.  
  
 **Evitar X** mediante identificadores que están en conflicto con las palabras clave de ampliamente utilizado lenguajes de programación.  
  
 Según la regla 4 de Common Language Specification \(CLS\), todos los lenguajes compatibles con deben proporcionar un mecanismo que permite el acceso a elementos con nombre que utilizar una palabra clave de ese idioma como identificador. C\#, por ejemplo, utiliza el signo como un mecanismo de escape en este caso @. Sin embargo, todavía es una buena idea evitar palabras clave comunes porque es mucho más difícil de usar un método con la secuencia de escape que uno sin él.  
  
## Uso de las abreviaturas y acrónimos  
 **X no** utilice abreviaturas ni contracciones como parte de los nombres de identificador.  
  
 Por ejemplo, utilice `GetWindow` en lugar de `GetWin`.  
  
 **X no** utilice cualquier ningún acrónimo que no es ampliamente aceptado e incluso si lo son, sólo cuando sea necesario.  
  
## Evitar los nombres específicos de lenguaje  
 **✓ hacer** utilice nombres con interés semántico en lugar de palabras clave específicas del idioma para nombres de tipo.  
  
 Por ejemplo, `GetLength` es mejor nombre que `GetInt`.  
  
 **✓ hacer** utilizar un nombre de tipo genérico de CLR, en lugar de un nombre de idioma específico, en casos raros cuando un identificador no tiene ningún significado semántico más allá de su tipo.  
  
 Por ejemplo, un método de conversión a <xref:System.Int64> deben llamarse `ToInt64`, no `ToLong` \(porque <xref:System.Int64> es un nombre CLR para C\#\-alias específico `long`\). La tabla siguiente presenta varios tipos de base de datos utilizando los nombres de tipo CLR \(así como los nombres de tipo correspondiente para C\#, Visual Basic y C\+\+\).  
  
|C\#|Visual Basic|C\+\+|CLR|  
|---------|------------------|-----------|---------|  
|**sbyte**|**SByte**|**char**|**SByte**|  
|**byte**|**Byte**|**unsigned char**|**Byte**|  
|**short**|**Corto**|**short**|**Int16**|  
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|  
|**int**|**Integer**|**int**|**Int32**|  
|**uint**|**UInt32**|**unsigned int**|**UInt32**|  
|**long**|**Long**|**\_\_int64**|**Int64**|  
|**ulong**|**UInt64**|**unsigned \_\_int64**|**UInt64**|  
|**float**|**Single**|**float**|**Single**|  
|**double**|**Doble**|**double**|**Doble**|  
|**bool**|**Booleano**|**bool**|**Booleano**|  
|**char**|**Char**|**wchar\_t**|**Char**|  
|**string**|**String**|**String**|**String**|  
|**objeto**|**Objeto**|**Objeto**|**Objeto**|  
  
 **✓ hacer**  utilizar un nombre común, como `value` o `item`, en lugar de repetir el nombre de tipo, en casos raros cuando un identificador no tiene ningún significado semántico y el tipo del parámetro no es importante.  
  
## Nomenclatura de las nuevas versiones de API existentes  
 **✓ hacer** utilizar un nombre similar a la API antigua al crear nuevas versiones de una API existente.  
  
 Esto ayuda a resaltar la relación entre las API.  
  
 **✓ hacer** prefiera agregar un sufijo, en lugar de un prefijo para indicar una nueva versión de una API existente.  
  
 Esto le ayudará a detección al examinar la documentación, o mediante Intellisense. La versión anterior de la API se organizarán cerca de las nuevas API, porque la mayoría de los exploradores y Intellisense muestran los identificadores en orden alfabético.  
  
 **✓ considere** con un identificador nuevo, pero significativo, en lugar de agregar un prefijo o un sufijo.  
  
 **✓ hacer** use un sufijo numérico para indicar una nueva versión de una API existente, especialmente si el nombre de la API existente es el único nombre que tenga sentido \(por ejemplo, si es un estándar del sector\) y si agregar significativo cualquier sufijo \(o cambiar el nombre\) no es una opción adecuada.  
  
 **X no** utilizar "Ex" \(o similar\) sufijo para un identificador para distinguir de una versión anterior de la misma API.  
  
 **✓ hacer** utilizar el sufijo "64" al introducir las versiones de API que operan en un entero de 64 bits \(un entero largo\) en lugar de un entero de 32 bits. Sólo necesitará adoptar este enfoque cuando exista la API de 32 bits existente. no lo haga para la nuevas API con sólo una versión de 64 bits.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)