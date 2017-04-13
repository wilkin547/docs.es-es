---
title: "Tipos anidados | Microsoft Docs"
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
  - "tipos anidados"
  - "tipos anidados públicos"
  - "instrucciones de diseño de tipo, los tipos anidados"
  - "tipos anidados"
  - "tipo de miembros [.NET Framework]"
  - "tipos de instrucciones [.NET Framework], anidadas de diseño de biblioteca de clase"
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Tipos anidados
Un tipo anidado es un tipo definido dentro del ámbito de otro tipo, que se denomina el tipo envolvente. Un tipo anidado tiene acceso a todos los miembros de su tipo envolvente. Por ejemplo, tiene acceso a campos privados definidos en el tipo envolvente y proteger los campos definidos en todos los antecesores del tipo envolvente.  
  
 En general, los tipos anidados deben usarse con moderación. Hay varias razones para ello. Algunos desarrolladores no están completamente familiarizados con el concepto. Estos desarrolladores por ejemplo, podrían tener problemas con la sintaxis de declaración de variables de tipos anidados. Los tipos anidados son también muy estrechamente con sus tipos envolventes y como tal no son adecuados para los tipos de uso general.  
  
 Los tipos anidados son más adecuados para el modelado de los detalles de implementación de sus tipos envolventes. El usuario final rara vez deberían tener que declarar las variables de un tipo anidado y casi nunca es necesario crear explícitamente instancias de tipos anidados. Por ejemplo, el enumerador de una colección puede ser un tipo anidado de esa colección. Normalmente se crean instancias de los enumeradores por su tipo envolvente, y dado que muchos lenguajes admiten la instrucción foreach, variables de enumerador rara vez tienen que declararse el usuario final.  
  
 **✓ hacer** utilizar tipos anidados cuando la relación entre el tipo anidado y su tipo exterior es tal que es deseable la semántica de accesibilidad de miembros.  
  
 **X no** uso de tipos anidados públicos como una agrupación lógica construir; usar espacios de nombres para este.  
  
 **Evitar X** exponer públicamente los tipos anidados. La única excepción a esto es si necesitan declararse sólo en escenarios poco habituales, como el uso de subclases u otros escenarios de personalización avanzada variables del tipo anidado.  
  
 **X no** utilice tipos anidados si el tipo es probable que se hace referencia fuera del tipo contenedor.  
  
 Por ejemplo, una enumeración que se pasa a un método definido en una clase no se debe definir como un tipo anidado en la clase.  
  
 **X no** utilice tipos anidados si es necesario crear una instancia por código de cliente.  Si un tipo tiene un constructor público, probablemente no debería anidarse.  
  
 Si un tipo se puede crear instancias, que parece indicar que el tipo tiene un lugar en el marco de trabajo en su propio \(puede crearlo, trabajar con él y destruir sin necesidad de utilizar el tipo exterior\) y, por tanto, no pueden anidarse. Tipos internos no deberían reutilizar ampliamente fuera del tipo externo sin ninguna relación con el tipo externo.  
  
 **X no** define un tipo anidado como un miembro de una interfaz. Muchos lenguajes no admiten este tipo de construcción.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)