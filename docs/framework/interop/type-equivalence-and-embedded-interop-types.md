---
title: "Type Equivalence and Embedded Interop Types | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "type equivalence"
  - "embedded interop types"
  - "primary interop assemblies,not necessary in CLR version 4"
  - "NoPIA"
ms.assetid: 78892eba-2a58-4165-b4b1-0250ee2f41dc
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Type Equivalence and Embedded Interop Types
A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Common Language Runtime es compatible con la incrustación de información de tipos para los tipos COM directamente en los ensamblados administrados, en lugar de exigir a los ensamblados administrados que obtengan información de tipos para los tipos COM de los ensamblados de interoperabilidad.  Dado que la información de tipos incrustada incluye solo los tipos y miembros que utilizan realmente un ensamblado administrado, dos ensamblados administrados pueden tener vistas muy diferentes del mismo tipo COM.  Cada ensamblado administrado tiene un objeto <xref:System.Type> diferente para representar la vista del tipo COM.  Common Language Runtime es compatible con la equivalencia de tipos entre estas distintas vistas para interfaces, estructuras, enumeraciones y delegados.  
  
 La equivalencia de tipos significa que un objeto COM que pasa de un ensamblado administrado a otro se puede convertir al tipo administrado adecuado en el ensamblado receptor.  
  
> [!NOTE]
>  La equivalencia de tipos y los tipos de interoperabilidad incrustados simplifican la implementación de aplicaciones y complementos que utilizan componentes COM, porque no es necesario implementar ensamblados de interoperabilidad con las aplicaciones.  Los desarrolladores de componentes COM compartidos deben seguir creando ensamblados de interoperabilidad primarios \(PIA\) si desean poder utilizar sus componentes en versiones anteriores de .NET Framework.  
  
## Equivalencia de tipos  
 La equivalencia de tipos COM es compatible con interfaces, estructuras, enumeraciones y delegados.  Los tipos COM se califican como equivalentes si se cumplen los siguientes requisitos en su totalidad:  
  
-   Los tipos son ambos interfaces o ambos estructuras o ambos enumeraciones o ambos delegados.  
  
-   Los tipos tienen la misma identidad, tal y como se describe en la sección siguiente.  
  
-   Ambos tipos son aptos para la equivalencia de tipos, tal y como se describe en la sección [Marcar tipos COM para la equivalencia de tipos](#type_equiv).  
  
### Identidad de tipo  
 Se determina que dos tipos tienen la misma identidad cuando sus ámbitos e identidades coinciden, en otras palabras, si ambos tienen el atributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> y los dos atributos tienen propiedades <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A> y <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> coincidentes.  En la comparación para <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> no se distingue entre mayúsculas y minúsculas.  
  
 Si un tipo no tiene el atributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> o si tiene un atributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> que no especifica ámbito ni identificador, aún así se puede tener en cuenta el tipo para la equivalencia del modo siguiente:  
  
-   Para las interfaces, se utiliza el valor de <xref:System.Runtime.InteropServices.GuidAttribute> en lugar de la propiedad <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A?displayProperty=fullName> y se utiliza la propiedad <xref:System.Type.FullName%2A?displayProperty=fullName> \(es decir, el nombre del tipo, incluido el espacio de nombres\) en lugar de la propiedad <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A?displayProperty=fullName>.  
  
-   Para estructuras, enumeraciones y delegados, se utiliza <xref:System.Runtime.InteropServices.GuidAttribute> del ensamblado contenedor en lugar de la propiedad <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Scope%2A> y la propiedad <xref:System.Type.FullName%2A?displayProperty=fullName> en lugar de la propiedad <xref:System.Runtime.InteropServices.TypeIdentifierAttribute.Identifier%2A>.  
  
<a name="type_equiv"></a>   
### Marcar tipos COM para la equivalencia de tipos  
 Puede marcar un tipo como apto para la equivalencia de tipos de dos maneras:  
  
-   Aplique el atributo <xref:System.Runtime.InteropServices.TypeIdentifierAttribute> al tipo.  
  
-   Convierta el tipo en un tipo de importación COM.  Una interfaz es un tipo de importación COM si tiene el atributo <xref:System.Runtime.InteropServices.ComImportAttribute>.  Una interfaz, estructura, enumeración o delegado es un tipo de importación COM si el ensamblado en el que está definido tiene el atributo <xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>.  
  
## Vea también  
 <xref:System.Type.IsEquivalentTo%2A>   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/es-es/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)