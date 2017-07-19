---
title: "Asignar nombres a recursos | Microsoft Docs"
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
  - "recursos localizados de nombres [.NET Framework]"
  - "localización, instrucciones de nomenclatura"
  - "nombres de recursos"
  - "aplicaciones globales, instrucciones de nomenclatura"
  - "aplicaciones internacionales, instrucciones de nomenclatura"
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Asignar nombres a recursos
Dado que los recursos localizables se pueden hacer referencia a través de ciertos objetos como si fueran propiedades, las instrucciones de nomenclatura de recursos son similares a las directrices de la propiedad.  
  
 **✓ hacer** usar Pascal en las claves de recursos.  
  
 **✓ hacer** proporcionar descriptivos en lugar de identificadores corto.  
  
 **X no** usar palabras clave específicas del idioma de los principales lenguajes CLR.  
  
 **✓ hacer** utilice sólo caracteres alfanuméricos y caracteres de subrayado en nombres de recursos.  
  
 **✓ hacer** usa la siguiente convención de nomenclatura para los recursos de mensaje de excepción.  
  
 El identificador de recurso debe ser el nombre de tipo de excepción más un identificador corto de la excepción:  
  
 `ArgumentExceptionIllegalCharacters`   
 `ArgumentExceptionInvalidName`   
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)