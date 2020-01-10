---
title: Diseño de clases estáticas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 35bcf1d403c78cdfcbb476b2eb5de2251a564b9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709067"
---
# <a name="static-class-design"></a>Diseño de clases estáticas
Una clase estática se define como una clase que solo contiene miembros estáticos (por supuesto, además de los miembros de instancia heredados de <xref:System.Object?displayProperty=nameWithType> y posiblemente un constructor privado). Algunos lenguajes proporcionan compatibilidad integrada con las clases estáticas. En C# 2,0 y versiones posteriores, cuando una clase se declara como estática, es Sealed, abstract, y ningún miembro de instancia se puede invalidar o declarar.  
  
 Las clases estáticas son un compromiso entre el diseño y la simplicidad orientados a objetos puros. Normalmente se utilizan para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), a los titulares de métodos de extensión o a la funcionalidad para la que no se garantiza un contenedor orientado a objetos completo (como <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ DO** usan clases estáticas con moderación.  
  
 Las clases estáticas solo se deben usar como clases de soporte para el núcleo orientado a objetos del marco.  
  
 **X DO NOT** tratar las clases estáticas como un depósito varios.  
  
 **X DO NOT** declarar o invalidar los miembros de instancia en clases estáticas.  
  
 **✓ DO** declarar las clases estáticas como sellada, abstract y agregue un constructor de instancia privada, si su lenguaje de programación no tiene compatibilidad integrada para las clases estáticas.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
