---
title: "Diseño de constructores"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 66a297ed035f5afde06913b89f1f92dee5745f48
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="constructor-design"></a>Diseño de constructores
Hay dos tipos de constructores: escriba constructores y los constructores de instancia.  
  
 Constructores de tipos son estáticos y se ejecutan mediante CLR antes de que se utiliza el tipo. Constructores de instancias se ejecutan cuando se crea una instancia de un tipo.  
  
 Constructores de tipo no toman ningún parámetro. Constructores de instancias pueden. Constructores de instancias que no toman ningún parámetro a menudo se denominan constructores predeterminados.  
  
 Los constructores son la forma más natural para crear instancias de un tipo. Mayoría de los desarrolladores buscará y pruebe a utilizar un constructor antes de que consideren formas alternativas de creación de instancias (por ejemplo, los métodos de fábrica).  
  
 **✓ Considere la posibilidad de** proporcionar simple, lo ideal es que el valor predeterminado, constructores.  
  
 Un constructor simple tiene un número muy pequeño de parámetros y todos los parámetros son tipos primitivos o enumeraciones. Estos constructores simples aumentan la usabilidad de framework.  
  
 **✓ Considere la posibilidad de** mediante un método de generador estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si no parece natural siguiendo las directrices de diseño del constructor.  
  
 **✓ HACER** usar los parámetros de constructor como accesos directos para establecer las propiedades principales.  
  
 No debería haber ninguna diferencia semántica entre usando el constructor vacío seguido por algunos conjuntos de propiedades y utilizando un constructor con varios argumentos.  
  
 **✓ HACER** utilizar el mismo nombre para los parámetros de constructor y una propiedad si los parámetros del constructor se utilizan simplemente para establecer la propiedad.  
  
 La única diferencia entre estos parámetros y las propiedades debe ser las mayúsculas y minúsculas.  
  
 **✓ HACER** un trabajo mínimo en el constructor.  
  
 Constructores no deberían hacer mucho trabajo que no sea de captura de los parámetros del constructor. El costo de cualquier otro procesamiento se debería retrasar hasta que requiere.  
  
 **✓ HACER** genere excepciones desde los constructores de instancia, si procede.  
  
 **✓ HACER** declarar explícitamente el constructor predeterminado público en clases, si se requiere un constructor de ese tipo.  
  
 Si no se declara explícitamente ningún constructor en un tipo, muchos lenguajes (por ejemplo, C#) agregará automáticamente un constructor predeterminado público. (Las clases abstractas obtener un constructor protegido).  
  
 Agregar un constructor con parámetros a una clase, impide que el compilador agregue el constructor predeterminado. Esto hace que a menudo cambios accidentales.  
  
 **X evitar** la definición explícita de constructores predeterminados en estructuras.  
  
 Esto acelera la creación de una matriz, porque si no se define el constructor predeterminado, no tiene que ejecutarse en todas las ranuras de la matriz. Tenga en cuenta que muchos compiladores, incluyendo C#, no permiten las estructuras que tienen constructores sin parámetros por esta razón.  
  
 **X evitar** al llamar a los miembros virtuales en un objeto dentro de su constructor.  
  
 Llamar a un miembro virtual hará que la invalidación más derivada llamarlo, incluso si el constructor del tipo más derivado no ha sido totalmente ejecutado todavía.  
  
### <a name="type-constructor-guidelines"></a>Directrices de Constructor de tipo  
 **✓ HACER** hacer privado static (constructores).  
  
 Un constructor estático, que también se denomina un constructor de clase, se utiliza para inicializar un tipo. CLR llama al constructor estático antes de crear la primera instancia del tipo o se llama a cualquier miembro estático en ese tipo. El usuario no tiene ningún control sobre cuándo se llama al constructor estático. Si un constructor estático no es privado, se puede llamar mediante código que no sea de CLR. Dependiendo de las operaciones realizadas en el constructor, esto puede provocar un comportamiento inesperado. El compilador de C# fuerza constructores estáticos a ser privado.  
  
 **X DO NOT** genere excepciones desde constructores estáticos.  
  
 Si se produce una excepción desde un constructor de tipo, el tipo no es utilizable en el dominio de aplicación actual.  
  
 **Considere la posibilidad de ✓** inicializar campos estáticos en línea, en lugar de utilizar explícitamente constructores estáticos, como el tiempo de ejecución se puede optimizar el rendimiento de tipos que no tienen un constructor estático definido explícitamente.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
