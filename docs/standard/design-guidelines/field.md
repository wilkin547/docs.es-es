---
title: "Dise&#241;o de campos | Microsoft Docs"
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
  - "campos, instrucciones de diseño"
  - "campos de sólo lectura"
  - "instrucciones de diseño de miembros, campos"
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Dise&#241;o de campos
El principio de encapsulación es uno de los conceptos más importantes en el diseño orientado a objetos. Este principio indica que los datos almacenados dentro de un objeto deben ser accesibles sólo a ese objeto.  
  
 Una forma útil de interpretar el principio consiste en indicar que un tipo debe diseñarse para que se pueden realizar cambios en los campos de ese tipo \(cambios de nombre o tipo\) sin interrumpir el código distinto para los miembros del tipo. Esta interpretación inmediatamente implica que todos los campos deben ser privados.  
  
 Se exclusión campos estáticos y constantes de sólo lectura de esta restricción estricta, porque esos campos casi por definición, nunca deben cambiar.  
  
 **X no** proporcione campos de instancia públicos sean protegidos.  
  
 Debe proporcionar propiedades para tener acceso a los campos en vez de hacerlos públicos o protegidos.  
  
 **✓ hacer** Utilice campos constantes para las constantes que no se va a cambiar nunca.  
  
 El compilador quema los valores de los campos const directamente en el código de llamada. Por lo tanto, los valores constantes nunca pueden cambiarse sin correr el riesgo de interrumpir la compatibilidad.  
  
 **✓ hacer** usar estática pública `readonly` campos de instancias de objetos predefinidas.  
  
 Si hay instancias predefinidas del tipo, declárelos como públicos campos estáticos de sólo lectura del propio tipo.  
  
 **X no** asignar instancias de tipos mutables `readonly` campos.  
  
 Un tipo que mutable es un tipo con instancias que se pueden modificar cuando se crea una instancia. Por ejemplo, secuencias, mayoría de las colecciones y matrices son tipos mutables, pero <xref:System.Int32?displayProperty=fullName>, <xref:System.Uri?displayProperty=fullName>, y <xref:System.String?displayProperty=fullName> todos son inmutables. El modificador de solo lectura en un campo de tipo de referencia impide que la instancia almacenada en el campo que se reemplace, pero impedir que los datos de instancia del campo se modifique llamando a los miembros cambiar la instancia.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)