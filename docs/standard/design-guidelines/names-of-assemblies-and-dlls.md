---
title: Nombres de ensamblados y bibliotecas DLL
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97bd152cff53fb1c2edb107b6d6b34bd91ca1c49
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44366952"
---
# <a name="names-of-assemblies-and-dlls"></a>Nombres de ensamblados y bibliotecas DLL
Un ensamblado es la unidad de implementación y la identidad para los programas de código administrado. Aunque los ensamblados pueden abarcar uno o varios archivos, normalmente se asigna uno a uno con un archivo DLL de un ensamblado. Por lo tanto, en esta sección se describen sola convenciones de nomenclatura de DLL, que, a continuación, se pueden asignar a las convenciones de nomenclatura del ensamblado.  
  
 **✓ DO** elegir nombres para el ensamblado DLL que sugieran grandes fragmentos de funcionalidad como System.Data.  
  
 No tienen nombres de ensamblado y el archivo DLL que se corresponden con los espacios de nombres, pero es razonable seguir el espacio de nombres al asignar nombres a los ensamblados. Una buena regla general es el nombre del archivo DLL según el prefijo común de los espacios de nombres del ensamblado. Por ejemplo, un ensamblado con dos espacios de nombres, `MyCompany.MyTechnology.FirstFeature` y `MyCompany.MyTechnology.SecondFeature`, se podría llamar `MyCompany.MyTechnology.dll`.  
  
 **✓ CONSIDER** nomenclatura DLL según el modelo siguiente:  
  
 `<Company>.<Component>.dll`  
  
 donde `<Component>` contiene uno o más cláusulas separados por puntos. Por ejemplo:  
  
 `Litware.Controls.dll`.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
