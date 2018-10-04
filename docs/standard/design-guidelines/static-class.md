---
title: Diseño de clases estáticas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3a0a51fc6055190f9a0189de2e17d98f88036ea
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261581"
---
# <a name="static-class-design"></a>Diseño de clases estáticas
Se define una clase estática como una clase que contiene sólo miembros estáticos (por supuesto además de los miembros de instancia heredados de <xref:System.Object?displayProperty=nameWithType> y, posiblemente, un constructor privado). Algunos lenguajes ofrecen compatibilidad integrada para las clases estáticas. En C# 2.0 y versiones posteriores, cuando una clase se declara como estática, está sellada y abstracta y se puede invalidar o declarado ningún miembro de instancia.  
  
 Las clases estáticas son un compromiso entre el diseño orientado a objetos puro y simplicidad. Se suelen usar para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), los propietarios de los métodos de extensión o la funcionalidad para el que se no fundamentado un contenedor completa orientada a objetos (como <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ DO** usan clases estáticas con moderación.  
  
 Las clases estáticas deben usarse solo como clases auxiliares para las principales orientada a objetos de framework.  
  
 **X DO NOT** tratar las clases estáticas como un depósito varios.  
  
 **X DO NOT** declarar o invalidar los miembros de instancia en clases estáticas.  
  
 **✓ DO** declarar las clases estáticas como sellada, abstract y agregue un constructor de instancia privada, si su lenguaje de programación no tiene compatibilidad integrada para las clases estáticas.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
