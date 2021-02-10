---
description: 'Más información acerca de: Diseño de clases estáticas'
title: Diseño de clases estáticas
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 16db470ab0975a5545617c9c5471d6ac157e688b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782473"
---
# <a name="static-class-design"></a>Diseño de clases estáticas

Una clase estática se define como una clase que solo contiene miembros estáticos (por supuesto, además de los miembros de instancia heredados de <xref:System.Object?displayProperty=nameWithType> y posiblemente un constructor privado). Algunos lenguajes proporcionan compatibilidad integrada con las clases estáticas. En C# 2.0 y versiones posteriores, cuando una clase se declara como estática, está sellada, es abstracta y ningún miembro de instancia se puede invalidar ni declarar.

 Las clases estáticas son un compromiso entre el diseño y la simplicidad orientados a objetos puros. Normalmente se utilizan para proporcionar accesos directos a otras operaciones (como <xref:System.IO.File?displayProperty=nameWithType>), contenedores de métodos de extensión o una funcionalidad para la que no se garantiza un contenedor orientado a objetos completo (como <xref:System.Environment?displayProperty=nameWithType>).

 ✔️ USE las clases estáticas con moderación.

 Las clases estáticas solo se deben usar como clases de compatibilidad para el núcleo orientado a objetos del marco.

 ❌ NO trate las clases estáticas como un cubo diferente.

 ❌ NO declare ni invalide los miembros de instancia en las clases estáticas.

 ✔️ DECLARE las clases estáticas como selladas y abstractas, y agregue un constructor de instancia privado si su lenguaje de programación no tiene compatibilidad integrada con las clases estáticas.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de tipos](type.md)
- [Instrucciones de diseño de .NET Framework](index.md)
