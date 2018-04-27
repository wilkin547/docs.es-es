---
title: Nombres de ensamblados y bibliotecas DLL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ff14d3d804329e591486a7eb2a2ee7ed430f622c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="names-of-assemblies-and-dlls"></a>Nombres de ensamblados y bibliotecas DLL
Un ensamblado es la unidad de implementación e identidad de los programas de código administrado. Aunque los ensamblados pueden abarcar uno o más archivos, normalmente un ensamblado se asigna uno a uno con un archivo DLL. Por lo tanto, en esta sección se describen sola convenciones de nomenclatura de archivos DLL, que, a continuación, se pueden asignar a las convenciones de nomenclatura ensamblado.  
  
 **✓ HACER** elegir nombres para el ensamblado DLL que sugieran grandes fragmentos de funcionalidad como System.Data.  
  
 Nombres de ensamblado y el archivo DLL no tienen que corresponder con espacios de nombres, pero es razonable seguir el nombre de espacio de nombres al asignar nombres a los ensamblados. Una buena regla general es el nombre de la DLL basada en el prefijo común de los espacios de nombres incluidos en el ensamblado. Por ejemplo, un ensamblado con dos espacios de nombres, `MyCompany.MyTechnology.FirstFeature` y `MyCompany.MyTechnology.SecondFeature`, se podría llamar `MyCompany.MyTechnology.dll`.  
  
 **Considere la posibilidad de ✓** nomenclatura DLL según el modelo siguiente:  
  
 `<Company>.<Component>.dll`  
  
 donde `<Component>` contiene una o más cláusulas separados por puntos. Por ejemplo:  
  
 `Litware.Controls.dll`.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
