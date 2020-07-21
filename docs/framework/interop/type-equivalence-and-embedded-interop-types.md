---
title: Equivalencia de tipos y tipos de interoperabilidad incrustados
description: Comprenda la equivalencia de tipos entre los tipos y miembros de .NET con un ensamblado administrado y los tipos COM que se insertan en ese ensamblado. Para .NET 4 y versiones posteriores.
ms.date: 03/30/2017
helpviewer_keywords:
- type equivalence
- embedded interop types
- primary interop assemblies,not necessary in CLR version 4
- NoPIA
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
ms.openlocfilehash: 2d572133c42f01af7d50f6f771588f5173853f9a
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282013"
---
# <a name="type-equivalence-and-embedded-interop-types"></a>Equivalencia de tipos y tipos de interoperabilidad incrustados

A partir de .NET Framework 4, Common Language Runtime admite la incrustación de información de tipos COM directamente en ensamblados administrados, en lugar de exigir a los ensamblados administrados obtener información de tipos COM de ensamblados de interoperabilidad. Dado que la información de tipos incrustada solo incluye los tipos y miembros que realmente usa un ensamblado administrado, dos ensamblados administrados pueden tener vistas muy diferentes del mismo tipo COM. Cada ensamblado administrado tiene un objeto <xref:System.Type> diferente para representar su vista del tipo COM. Common Language Runtime admite la equivalencia de tipos entre estas distintas vistas de interfaces, estructuras, enumeraciones y delegados.

La equivalencia de tipos significa que un objeto COM que se pasa de un ensamblado administrado a otro se puede convertir al tipo administrado adecuado en el ensamblado receptor.

> [!NOTE]
> La equivalencia de tipos y los tipos de interoperabilidad incrustados simplifican la implementación de aplicaciones y complementos que usan componentes COM, porque no es necesario implementar ensamblados de interoperabilidad con las aplicaciones. Los desarrolladores de componentes COM compartidos siguen teniendo que crear ensamblados de interoperabilidad primarios (PIA) si quieren que las versiones anteriores de .NET Framework usen sus componentes.

## <a name="type-equivalence"></a>Equivalencia de tipos

 Se admite la equivalencia de tipos COM para interfaces, estructuras, enumeraciones y delegados. Los tipos COM se consideran equivalentes si se cumplen todas las condiciones siguientes:

- Ambos tipos son interfaces, estructuras, enumeraciones o delegados.

- Los tipos tienen la misma identidad, como se explica en la sección siguiente.

- Ambos tipos son aptos para la equivalencia de tipos, como se explica en la sección [Marcado de tipos COM para la equivalencia de tipos](#marking-com-types-for-type-equivalence).

### <a name="type-identity"></a>Identidad de tipos

Se considera que dos tipos tienen la misma identidad cuando sus ámbitos e identidades coinciden, es decir, si cada uno de ellos tiene el atributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> y los dos atributos tienen propiedades <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> y <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> coincidentes. La comparación de <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> no distingue mayúsculas de minúsculas.

Si un tipo no tiene el atributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute>, o si tiene un atributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> que no especifica ámbito ni identificador, se puede seguir considerando para la equivalencia como se indica a continuación:

- En las interfaces se usa el valor de la propiedad <xref:System.Runtime.InteropServices.GuidAttribute> en lugar de <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=nameWithType> y se emplea la propiedad <xref:System.Type.FullName%2A?displayProperty=nameWithType> (es decir, el nombre del tipo, incluido el espacio de nombres) en lugar de la propiedad <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=nameWithType>.

- En estructuras, enumeraciones y delegados, se usa el elemento <xref:System.Runtime.InteropServices.GuidAttribute> del ensamblado contenedor en lugar de la propiedad <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> y se emplea la propiedad <xref:System.Type.FullName%2A?displayProperty=nameWithType> en lugar de la propiedad <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A>.

### <a name="marking-com-types-for-type-equivalence"></a>Marcado de tipos COM para la equivalencia de tipos

 Puede marcar un tipo como apto para la equivalencia de tipos de dos maneras:

- Aplique el atributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> al tipo.

- Convierta el tipo en un tipo de importación de COM. Una interfaz es un tipo de importación de COM si tiene el atributo <xref:System.Runtime.InteropServices.ComImportAttribute>. Una interfaz, una estructura, una enumeración o un delegado es un tipo de importación de COM si el ensamblado en el que se define tiene el atributo <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>.

## <a name="see-also"></a>Vea también

- <xref:System.Type.IsEquivalentTo%2A>
- [Uso de tipos COM en código administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Importar una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md)
