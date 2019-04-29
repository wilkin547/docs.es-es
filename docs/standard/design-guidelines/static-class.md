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
author: KrzysztofCwalina
ms.openlocfilehash: d0a2f11b53f50f2ec2f301f7b88df65e1cd7b811
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762051"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
