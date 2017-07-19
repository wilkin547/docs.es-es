---
title: "Dise&#241;o de la interfaz | Microsoft Docs"
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
  - "interfaces [.NET Framework], instrucciones de diseño"
  - "instrucciones de diseño de tipos, interfaces"
  - "instrucciones de diseño clases biblioteca [.NET Framework], interfaces"
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Dise&#241;o de la interfaz
Aunque la mayoría de las API se modela mejor mediante las clases y structs, hay casos en los que interfaces son más adecuadas o son la única opción.  
  
 El CLR no admite herencia múltiple \(es decir, las clases CLR no pueden heredar de más de una clase base\), pero permite tipos para implementar una o más interfaces además de heredar de una clase base. Por lo tanto, las interfaces se utilizan a menudo para lograr el efecto de herencia múltiple. Por ejemplo, <xref:System.IDisposable> es una interfaz que permite que los tipos admitir disposability independiente de cualquier otra jerarquía de herencia en el que desea participar.  
  
 Es la situación en que definir una interfaz es adecuada en la creación de una interfaz común que puede ser compatible con varios tipos, incluidos algunos tipos de valor. Tipos de valor no pueden heredar de tipos distintos de <xref:System.ValueType>, pero pueden implementar interfaces, por lo que usar una interfaz es la única opción para proporcionar un tipo base común.  
  
 **✓ hacer** defina una interfaz si necesita algunas API común para ser compatible con un conjunto de tipos que incluye los tipos de valor.  
  
 **✓ considere** define una interfaz si necesita admitir su funcionalidad en tipos que ya heredan de algún otro tipo.  
  
 **Evitar X** mediante las interfaces de marcador \(interfaces sin miembros\).  
  
 Si necesita marcar una clase como si tuviera una característica específica \(marcador\), en general, utilice un atributo personalizado en lugar de una interfaz.  
  
 **✓ hacer** proporcionar al menos un tipo que es una implementación de una interfaz.  
  
 Haciendo esto ayuda a validar el diseño de la interfaz. Por ejemplo, <xref:System.Collections.Generic.List%601> es una implementación de la <xref:System.Collections.Generic.IList%601> interfaz.  
  
 **✓ hacer** proporcionan al menos una API que consume cada interfaz definida \(un método que recibe la interfaz como un parámetro o una propiedad de tipo que la interfaz\).  
  
 Haciendo esto ayuda a validar el diseño de la interfaz. Por ejemplo, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=fullName> consume el <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> interfaz.  
  
 **X no** agregar miembros a una interfaz que ya se envió.  
  
 Al hacerlo, se interrumpiría implementaciones de la interfaz. Debe crear una nueva interfaz con el fin de evitar problemas de versiones.  
  
 Excepto en los casos descritos en estas instrucciones, en general, debería, elija clases en lugar de interfaces para diseñar bibliotecas reutilizables de código administrado.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)