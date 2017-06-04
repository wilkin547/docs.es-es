---
title: "Miembros protegidos | Microsoft Docs"
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
  - "miembros protegidos [.NET Framework]"
  - "miembros protegidos"
  - "sellados de clases [.NET Framework]"
  - "miembros protegidos de clases [.NET Framework]"
  - "clases no selladas"
  - "Personalizar comportamiento de clase"
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Miembros protegidos
Miembros protegidos por sí solos no proporcionan ninguna extensibilidad, pero pueden hacer más eficaz extensibilidad a través de la creación de subclases. Que pueden utilizarse para exponer las opciones de personalización avanzada sin complicar innecesariamente la interfaz pública principal.  
  
 Diseñadores de Framework deben tener cuidado con los miembros protegidos porque el nombre "protegido" puede dar una falsa sensación de seguridad. Cualquiera es capaz de subclase de una clase no sellada y miembros de acceso protegido y, por lo que los mismos defensivas prácticas de codificación utilizadas para los miembros públicos se aplican a los miembros protegidos.  
  
 **✓, considere la posibilidad de** mediante protegida miembros para la personalización avanzada.  
  
 **✓ hacer** trate los miembros protegidos de clases no selladas como públicos a efectos de seguridad, documentación y análisis de compatibilidad.  
  
 Cualquier persona puede heredar de una clase y tener acceso a los miembros protegidos.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Diseñar extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)