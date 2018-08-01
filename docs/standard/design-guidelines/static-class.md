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
ms.openlocfilehash: 92152600d317c04e3fef26400b11e94a549fde4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571064"
---
# <a name="static-class-design"></a>Diseño de clases estáticas
Una clase estática se define como una clase que contiene sólo miembros estáticos (evidentemente además de los miembros de instancia se hereda de <xref:System.Object?displayProperty=nameWithType> y posiblemente un constructor privado). Algunos lenguajes proporcionan compatibilidad integrada para las clases estáticas. En C# 2.0 y versiones posteriores, cuando una clase se declara como estático, lo abstracto, está sellada y ningún miembro de instancia se puede invalidar o declarado.  
  
 Las clases estáticas son una solución intermedia entre puro diseño orientado a objetos y la simplicidad. Se suelen usar para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), los propietarios de los métodos de extensión, o la funcionalidad para el que se no justificado un contenedor completa orientada a objetos (como <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ DO** usan clases estáticas con moderación.  
  
 Las clases estáticas deben utilizarse únicamente como clases auxiliares para el núcleo orientada a objetos de framework.  
  
 **X DO NOT** tratar las clases estáticas como un depósito varios.  
  
 **X DO NOT** declarar o invalidar los miembros de instancia en clases estáticas.  
  
 **✓ DO** declarar las clases estáticas como sellada, abstract y agregue un constructor de instancia privada, si su lenguaje de programación no tiene compatibilidad integrada para las clases estáticas.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de tipos](../../../docs/standard/design-guidelines/type.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
