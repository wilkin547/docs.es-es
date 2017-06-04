---
title: "Clases base para implementar abstracciones | Microsoft Docs"
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
  - "abstracciones [.NET Framework]"
  - "clases base, abstracciones"
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Clases base para implementar abstracciones
En sentido estricto, una clase se convierte en una clase base cuando otra clase se deriva de él. En esta sección, sin embargo, una clase base es una clase que se han diseñado principalmente para proporcionar una abstracción común o para que otras clases reutilizar parte implementación aunque la herencia predeterminada. Clases base normalmente se encuentran en medio de las jerarquías de herencia entre una abstracción en la raíz de una jerarquía y varias implementaciones personalizadas en la parte inferior.  
  
 Sirven como aplicaciones auxiliares de implementación para implementar abstracciones. Por ejemplo, una de las abstracciones del marco de trabajo para colecciones ordenadas de elementos es el <xref:System.Collections.Generic.IList%601> interfaz. Implementación de <xref:System.Collections.Generic.IList%601> no es trivial, y por lo tanto, el marco de trabajo proporciona varias clases bases, como <xref:System.Collections.ObjectModel.Collection%601> y <xref:System.Collections.ObjectModel.KeyedCollection%602>, que sirven como aplicaciones auxiliares para implementar colecciones personalizadas.  
  
 Clases base normalmente no son adecuadas para actuar como abstracciones por sí mismos, ya que tienden a contener demasiados implementación. Por ejemplo, el `Collection<T>` clase base contiene una gran cantidad de implementación relacionados con el hecho de que implementa la no genérica `IList` interfaz \(para integrarse mejor con colecciones no genéricas\) y al hecho de que es una colección de elementos almacenados en la memoria en uno de sus campos.  
  
 Como se explicó anteriormente, las clases base pueden proporcionar ayuda inestimable para usuarios que necesitan para implementar abstracciones, pero al mismo tiempo pueden ser una responsabilidad importante. Agregar área de superficie y como aumentar la profundidad de las jerarquías de herencia y así conceptualmente complicar el marco de trabajo. Por lo tanto, las clases base deben usarse únicamente si proporcionan un valor significativo a los usuarios de framework. Debe evitarse si proporciona el valor sólo para los implementadores de framework, en el que caso delegación a una implementación interna en lugar de la herencia de una clase base debe tener en cuenta.  
  
 **✓ considere** abstracto de clases de base que incluso si no contienen ningún miembro abstracto. Esto indica claramente a los usuarios que la clase está diseñada únicamente para heredarse.  
  
 **✓ considere** colocar las clases base en un espacio de nombres independiente de los tipos de escenario principal. Por definición, las clases base están pensadas para escenarios de extensibilidad avanzados y, por tanto, no son interesantes para la mayoría de los usuarios.  
  
 **Evitar X** nomenclatura de clases bases con el sufijo "Base" si la clase está diseñada para su uso en las API públicas.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)   
 [Diseñar extensibilidad](../../../docs/standard/design-guidelines/designing-for-extensibility.md)