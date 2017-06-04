---
title: "Dise&#241;o de clases est&#225;ticas | Microsoft Docs"
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
  - "Escriba las instrucciones de diseño de clases estáticas"
  - "instrucciones de diseño clases biblioteca [.NET Framework], clases"
  - "clases [.NET Framework], estáticas"
  - "clases estáticas [.NET Framework]"
  - "clases [.NET Framework], instrucciones de diseño"
  - "Escriba las instrucciones de diseño de clases"
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Dise&#241;o de clases est&#225;ticas
Se define una clase estática como una clase que contiene sólo miembros estáticos \(por supuesto además de los miembros de instancia heredados de <xref:System.Object?displayProperty=fullName> y posiblemente un constructor privado\). Algunos lenguajes proporcionan compatibilidad integrada para las clases estáticas. En C\# 2.0 y versiones posteriores, cuando una clase se declara como estático, lo abstracto, está sellada y ningún miembro de instancia se puede invalidar o declarado.  
  
 Las clases estáticas son un compromiso entre el diseño orientado a objetos puro y simplicidad. Se utilizan habitualmente para proporcionar accesos directos a otras operaciones \(como <xref:System.IO.File?displayProperty=fullName>\), titulares de métodos de extensión o funcionalidad que se no justificado un contenedor completa orientada a objetos \(como <xref:System.Environment?displayProperty=fullName>\).  
  
 **✓ hacer** utilizar clases estáticas con moderación.  
  
 Las clases estáticas deben usarse únicamente como clases auxiliares para el núcleo orientada a objetos de framework.  
  
 **X no** tratar las clases estáticas como un depósito vario.  
  
 **X no** declare ni reemplace miembros de instancia en clases estáticas.  
  
 **✓ hacer** declarar clases estáticas como selladas, abstract y agregue un constructor de instancia privada, si su lenguaje de programación no tiene compatibilidad integrada para las clases estáticas.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)