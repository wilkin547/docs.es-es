---
title: Diseño de interfaces
ms.date: 10/22/2008
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: 6f8cbb757ffb42f63903b212fee33cdcbba7ecb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727684"
---
# <a name="interface-design"></a>Diseño de interfaces

Aunque la mayoría de las API se modelan mejor mediante clases y Structs, hay casos en los que las interfaces son más adecuadas o son la única opción.

 CLR no admite la herencia múltiple (es decir, las clases CLR no pueden heredar de más de una clase base), pero permite que los tipos implementen una o varias interfaces además de heredar de una clase base. Por lo tanto, las interfaces se usan a menudo para lograr el efecto de la herencia múltiple. Por ejemplo, <xref:System.IDisposable> es una interfaz que permite que los tipos admitan la eliminación independientemente de cualquier otra jerarquía de herencia en la que deseen participar.

 La otra situación en la que la definición de una interfaz es adecuada es crear una interfaz común que pueda ser compatible con varios tipos, incluidos algunos tipos de valor. Los tipos de valor no pueden heredar de tipos distintos de <xref:System.ValueType> , pero pueden implementar interfaces, por lo que el uso de una interfaz es la única opción para proporcionar un tipo base común.

 ✔️ definir una interfaz si necesita que una API común sea compatible con un conjunto de tipos que incluye tipos de valor.

 ✔️ considere la posibilidad de definir una interfaz si necesita admitir su funcionalidad en tipos que ya heredan de algún otro tipo.

 ❌ Evite el uso de interfaces de marcador (interfaces sin miembros).

 Si necesita marcar una clase como una característica específica (marcador), en general, use un atributo personalizado en lugar de una interfaz.

 ✔️ proporcionan al menos un tipo que es una implementación de una interfaz.

 Esto ayuda a validar el diseño de la interfaz. Por ejemplo, <xref:System.Collections.Generic.List%601> es una implementación de la <xref:System.Collections.Generic.IList%601> interfaz.

 ✔️ proporcionan al menos una API que consume cada interfaz que defina (un método que toma la interfaz como un parámetro o una propiedad con el tipo de interfaz).

 Esto ayuda a validar el diseño de la interfaz. Por ejemplo, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consume la <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interfaz.

 ❌ NO agregue miembros a una interfaz que se haya enviado anteriormente.

 Si lo hace, se interrumpirán las implementaciones de la interfaz. Debe crear una nueva interfaz con el fin de evitar problemas de control de versiones.

 A excepción de las situaciones descritas en estas instrucciones, debe, en general, elegir clases en lugar de interfaces al diseñar bibliotecas reutilizables de código administrado.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones de diseño de tipos](type.md)
- [Directrices de diseño de marco](index.md)
