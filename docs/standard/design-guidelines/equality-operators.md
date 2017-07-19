---
title: "Operadores de igualdad | Microsoft Docs"
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
  - "instrucciones de diseño clases biblioteca [.NET Framework], Equals (método)"
  - "instrucciones de diseño clases biblioteca [.NET Framework], operador de igualdad"
  - "operador de igualdad (==) [.NET Framework]"
  - "Equals (método)"
  - "== (operador de igualdad) [.NET Framework]"
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Operadores de igualdad
Esta sección describe la sobrecarga de operadores de igualdad y hace referencia a `operator==` y `operator!=` como operadores de igualdad.  
  
 **X no** uno de los operadores de igualdad y la otra sobrecarga.  
  
 **✓ hacer** Asegúrese de que <xref:System.Object.Equals%2A?displayProperty=fullName> y los operadores de igualdad tienen exactamente la misma semántica y las características de rendimiento similares.  
  
 Esto significa que a menudo `Object.Equals` debe reemplazarse cuando se sobrecargan los operadores de igualdad.  
  
 **Evitar X** iniciar excepciones desde los operadores de igualdad.  
  
 Por ejemplo, devolver false si uno de los argumentos es null en lugar de producir `NullReferenceException`.  
  
## Operadores de igualdad en los tipos de valor  
 **✓ hacer** sobrecargar los operadores de igualdad en los tipos de valor, si son iguales es significativo.  
  
 En la mayoría de los lenguajes de programación, no hay ninguna implementación predeterminada de `operator==` para tipos de valor.  
  
## Operadores de igualdad en los tipos de referencia  
 **Evitar X** sobrecarga de operadores de igualdad en los tipos de referencias mutables.  
  
 Muchos lenguajes tienen operadores de igualdad integrados para tipos de referencia. Los operadores integrados implementan generalmente la igualdad de referencia, y muchos desarrolladores se sorprenden cuando se cambia el comportamiento predeterminado para la igualdad de valor.  
  
 Este problema se soluciona para tipos de referencia inmutable porque inmutabilidad dificulta que debe tener en cuenta la diferencia entre la igualdad de referencia y la igualdad de valor.  
  
 **Evitar X** sobrecarga de operadores de igualdad en los tipos de referencia si la implementación sería mucho más lenta que el de igualdad de referencia.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de uso](../../../docs/standard/design-guidelines/usage-guidelines.md)