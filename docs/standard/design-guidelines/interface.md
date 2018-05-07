---
title: Diseño de interfaces
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dea5877f952869d5c84d6019617fcdc52d8ee0a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="interface-design"></a>Diseño de interfaces
Aunque la mayoría de las API se modela mejor mediante las clases y structs, hay casos en los que interfaces son más adecuadas o son la única opción.  
  
 El CLR no admite la herencia múltiple (es decir, las clases CLR no pueden heredar de más de una clase base), pero permite tipos para implementar una o más interfaces además de heredar de una clase base. Por lo tanto, las interfaces se utilizan a menudo para lograr el efecto de herencia múltiple. Por ejemplo, <xref:System.IDisposable> es una interfaz que permite que los tipos admitir disposability independiente de cualquier otra jerarquía de herencia en el que desean participar.  
  
 Es la situación en que definir una interfaz es adecuada en la creación de una interfaz común que puede ser compatible con varios tipos, incluidos algunos tipos de valor. Tipos de valor no pueden heredar de tipos distintos de <xref:System.ValueType>, pero pueden implementar interfaces, por lo que usar una interfaz es la única opción para proporcionar un tipo base común.  
  
 **✓ HACER** defina una interfaz si necesita algunas API comunes que deben admitir un conjunto de tipos que incluye los tipos de valor.  
  
 **✓ Considere la posibilidad de** define una interfaz si necesita admitir su funcionalidad en tipos que ya heredan de algún otro tipo.  
  
 **X evitar** mediante las interfaces de marcador (interfaces sin miembros).  
  
 Si necesita marcar una clase como si tuviera una característica específica (marcador), por lo general, utilice un atributo personalizado en lugar de una interfaz.  
  
 **✓ HACER** proporcionar al menos un tipo que es una implementación de una interfaz.  
  
 Haciendo esto ayuda a validar el diseño de la interfaz. Por ejemplo, <xref:System.Collections.Generic.List%601> es una implementación de la <xref:System.Collections.Generic.IList%601> interfaz.  
  
 **✓ HACER** proporcionan al menos una API que consuma cada interfaz definida (un método que toma la interfaz como un parámetro o una propiedad con tipo como la interfaz).  
  
 Haciendo esto ayuda a validar el diseño de la interfaz. Por ejemplo, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consume el <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfaz.  
  
 **X DO NOT** agregar miembros a una interfaz que se haya distribuido previamente.  
  
 Si lo hace, se interrumpiría las implementaciones de la interfaz. Debe crear una nueva interfaz con el fin de evitar problemas de control de versiones.  
  
 Excepto en los casos descritos en estas instrucciones, por lo general, debe, elegir las clases en lugar de interfaces diseñar bibliotecas reutilizables de código administrado.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
