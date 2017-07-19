---
title: "Nombres de ensamblados y archivos DLL | Microsoft Docs"
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
  - "nombres [.NET Framework], archivos DLL"
  - "nombres [.NET Framework], ensamblados"
  - "ensamblados [.NET Framework], nombres"
  - "DLL, nombres"
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Nombres de ensamblados y archivos DLL
Un ensamblado es la unidad de implementación e identidad de los programas de código administrado. Aunque los ensamblados pueden abarcar uno o más archivos, normalmente un ensamblado se asigna uno a uno con un archivo DLL. Por lo tanto, en esta sección se describe sólo convenciones de nomenclatura de archivos DLL, que, a continuación, se pueden asignar a las convenciones de nomenclatura ensamblado.  
  
 **✓ hacer** elegir nombres para el ensamblado de DLL que sugieran grandes fragmentos de funcionalidad como System.Data.  
  
 Nombres de ensamblado y el archivo DLL no tienen que corresponder con espacios de nombres, pero es razonable seguir el espacio de nombres al asignar nombres a los ensamblados. Una buena regla general es el nombre de la DLL basada en el prefijo común de los ensamblados incluidos en el ensamblado. Por ejemplo, un ensamblado con dos espacios de nombres, `MyCompany.MyTechnology.FirstFeature` y `MyCompany.MyTechnology.SecondFeature`, se podría llamar `MyCompany.MyTechnology.dll`.  
  
 **✓ considere** nomenclatura DLL según el modelo siguiente:  
  
 `<Company>.<Component>.dll`  
  
 donde `<Component>` contiene una o más cláusulas separadas por puntos. Por ejemplo:  
  
 `Litware.Controls.dll`.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)