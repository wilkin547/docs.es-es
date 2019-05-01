---
title: Nombres de ensamblados y bibliotecas DLL
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: KrzysztofCwalina
ms.openlocfilehash: 1aeef9e1be6e5fe747f440a8cb7f21095cb22f49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945501"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
