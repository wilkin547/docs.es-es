---
title: 'Comparación entre propiedades e indizadores: Guía de programación de C#'
description: Compare el modo en que los indexadores en C# se parecen a las propiedades. Excepto por algunas diferencias, las reglas que se definen para los descriptores de acceso de propiedad se aplican a los descriptores de acceso de indexador.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: fff20ca965e7614d26f7da32321a829d13292389
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192534"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>Comparación entre propiedades e indizadores (Guía de programación de C#)

Los indexadores son como propiedades. Excepto por las diferencias que se muestran en la tabla siguiente, todas las reglas que se definen para los descriptores de acceso de propiedad se aplican también a los descriptores de acceso de indexador.  
  
|Propiedad.|Indexador|  
|--------------|-------------|  
|Permite que los métodos se llamen como si fueran miembros de datos públicos.|Permite que se pueda tener acceso a los elementos de una colección interna de un objeto mediante la notación de matriz en el propio objeto.|  
|Se ha tenido acceso mediante un nombre simple.|Se ha tenido acceso mediante un índice.|  
|Puede ser un miembro de instancia o estático.|Debe ser un miembro de instancia.|  
|Un descriptor de acceso [get](../../language-reference/keywords/get.md) de una propiedad no tiene parámetros.|Un descriptor de acceso `get` de un indexador tiene la misma lista de parámetros formales que el indexador.|  
|Un descriptor de acceso [set](../../language-reference/keywords/set.md) de una propiedad contiene el parámetro `value` implícito.|Un descriptor de acceso `set` de un indexador tiene la misma lista de parámetros formales que el indexador, y también para el parámetro [value](../../language-reference/keywords/value.md).|  
|Admite la sintaxis abreviada con [Propiedades autoimplementadas](../classes-and-structs/auto-implemented-properties.md).|Admite miembros de cuerpo de expresión para obtener solo indexadores.|  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Indizadores](./index.md)
- [Propiedades](../classes-and-structs/properties.md)
