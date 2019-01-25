---
title: Diseño de interfaces
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: KrzysztofCwalina
ms.openlocfilehash: 1f982aa37f92b7270725574d949989ca120297d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660156"
---
# <a name="interface-design"></a>Diseño de interfaces
Aunque la mayoría de las API se modela mejor mediante las clases y structs, hay casos en que las interfaces son más adecuadas o son la única opción.  
  
 El CLR no admite herencia múltiple (es decir, las clases CLR no pueden heredar de más de una clase base), pero le permite implementar uno o más interfaces heredar una clase base además de los tipos. Por lo tanto, las interfaces se usan con frecuencia para lograr el efecto de herencia múltiple. Por ejemplo, <xref:System.IDisposable> es una interfaz que permite que los tipos admitir disposability independiente de cualquier otra jerarquía de herencia en el que desea participar.  
  
 Es la otra situación en que define una interfaz es adecuada en la creación de una interfaz común que puede ser compatibles con varios tipos, incluidos algunos tipos de valor. Tipos de valor no pueden heredar de tipos distintos de <xref:System.ValueType>, pero pueden implementar interfaces, por lo que usar una interfaz es la única opción para proporcionar un tipo base común.  
  
 **✓ DO** defina una interfaz si necesita algunas API comunes que deben admitir un conjunto de tipos que incluye los tipos de valor.  
  
 **✓ CONSIDER** define una interfaz si necesita admitir su funcionalidad en tipos que ya heredan de algún otro tipo.  
  
 **X AVOID** mediante las interfaces de marcador (interfaces sin miembros).  
  
 Si necesita marcar una clase como si tuviera una característica específica (marcador), en general, utilice un atributo personalizado en lugar de una interfaz.  
  
 **✓ DO** proporcionar al menos un tipo que es una implementación de una interfaz.  
  
 Si hace esto ayuda a validar el diseño de la interfaz. Por ejemplo, <xref:System.Collections.Generic.List%601> es una implementación de la <xref:System.Collections.Generic.IList%601> interfaz.  
  
 **✓ DO** proporcionan al menos una API que consuma cada interfaz definida (un método que toma la interfaz como un parámetro o una propiedad con tipo como la interfaz).  
  
 Si hace esto ayuda a validar el diseño de interfaz. Por ejemplo, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consume el <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfaz.  
  
 **X DO NOT** agregar miembros a una interfaz que se haya distribuido previamente.  
  
 Si lo hace, se interrumpirían implementaciones de la interfaz. Debe crear una nueva interfaz con el fin de evitar problemas de control de versiones.  
  
 Excepto para las situaciones descritas en estas instrucciones, en general, debería, elija clases en lugar de las interfaces para diseñar bibliotecas reutilizables de código administrado.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
