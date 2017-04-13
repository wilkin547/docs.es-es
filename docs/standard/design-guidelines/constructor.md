---
title: "Dise&#241;o de constructores | Microsoft Docs"
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
  - "instrucciones de diseño de miembro, constructores"
  - "constructores, instrucciones de diseño"
  - "constructores de instancias"
  - "constructores de tipos"
  - "miembros virtuales"
  - "constructores de tipos"
  - "constructores predeterminados"
  - "Static (constructores)"
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Dise&#241;o de constructores
Hay dos tipos de constructores: escriba constructores y los constructores de instancia.  
  
 Constructores de tipos son estáticos y se ejecutan en el CLR antes de utilizar el tipo. Los constructores de instancia se ejecutan cuando se crea una instancia de un tipo.  
  
 Constructores de tipos no toman ningún parámetro. Constructores de instancias pueden. Constructores de instancias que no toman ningún parámetro suelen denominarse constructores predeterminados.  
  
 Los constructores son la forma más natural para crear instancias de un tipo. La mayoría de los desarrolladores buscará y pruebe a utilizar un constructor antes de que consideren formas alternativas de creación de instancias \(por ejemplo, los métodos de fábrica\).  
  
 **✓ considere** proporcionar simple, idealmente predeterminados, los constructores.  
  
 Un constructor sencillo tiene un número muy pequeño de parámetros y todos los parámetros son tipos primitivos o enumeraciones. Estos constructores simples aumentan la usabilidad de framework.  
  
 **✓, considere la posibilidad de** mediante un método de generador estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si no parece natural seguir las instrucciones de diseño de constructor.  
  
 **✓ hacer** utilizar parámetros de constructor como accesos directos para establecer las propiedades principales.  
  
 No debería haber ninguna diferencia semántica entre utilizando el constructor vacío seguido de algunos conjuntos de propiedades y utilizando un constructor con varios argumentos.  
  
 **✓ hacer** utilizar el mismo nombre para los parámetros de constructor y una propiedad si los parámetros de constructor se utilizan simplemente para establecer la propiedad.  
  
 La única diferencia entre estos parámetros y las propiedades debería ser la grafía.  
  
 **✓ hacer** un trabajo mínimo en el constructor.  
  
 Constructores no deberían hacer mucho trabajo que no sea la captura de los parámetros del constructor. El costo de cualquier otro procesamiento se debería retrasar hasta que sean necesarios.  
  
 **✓ hacer** iniciar excepciones desde los constructores de instancia, si procede.  
  
 **✓ hacer** declarar explícitamente el constructor predeterminado público en clases, si se requiere un constructor de ese tipo.  
  
 Si no se declara explícitamente ningún constructor en un tipo, muchos lenguajes \(como C\#\) agregará automáticamente un constructor predeterminado público. \(Las clases abstractas obtener un constructor protegido\).  
  
 Agregando un constructor con parámetros a una clase, evita que el compilador agregue el constructor predeterminado. A menudo, esto provoca cambios accidentales.  
  
 **Evitar X** define explícitamente los constructores predeterminados en estructuras.  
  
 Esto acelera la creación de una matriz, porque si no se define el constructor predeterminado, no tiene que ejecutarse en todas las ranuras de la matriz. Tenga en cuenta que muchos compiladores, incluido C\# no permite que las estructuras tienen constructores sin parámetros para ello.  
  
 **Evitar X** al llamar a miembros virtuales en un objeto dentro de su constructor.  
  
 Llamar a un miembro virtual provocará el reemplazo más derivado que se llame, incluso si el constructor del tipo más derivado no ha sido totalmente ejecutado todavía.  
  
### Instrucciones de Constructor de tipos  
 **✓ hacer** hacer privado constructores estáticos.  
  
 Un constructor estático, también denominado constructor de clase, se utiliza para inicializar un tipo. CLR llama al constructor estático antes de crea la primera instancia del tipo o se llama a cualquier miembro estático en ese tipo. El usuario no tiene ningún control sobre cuándo se llama al constructor estático. Si un constructor estático no es privado, se puede llamar mediante código distinto de CLR. Dependiendo de las operaciones realizadas en el constructor, esto puede provocar un comportamiento inesperado. El compilador de C\# fuerza constructores estáticos sea privada.  
  
 **X no** iniciar excepciones desde los constructores estáticos.  
  
 Si se produce una excepción desde un constructor de tipo, el tipo no es utilizable en el dominio de aplicación actual.  
  
 **✓ considere** inicializar campos estáticos en línea en lugar de utilizar explícitamente constructores estáticos, como el tiempo de ejecución se puede optimizar el rendimiento de los tipos que no tienen un constructor estático definido explícitamente.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)