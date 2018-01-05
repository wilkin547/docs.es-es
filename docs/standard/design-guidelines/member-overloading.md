---
title: Sobrecarga de miembro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2c84d70fb8c05dc295fc807c9a59085c47d0f455
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="member-overloading"></a>Sobrecarga de miembro
Sobrecarga de miembro significa crear dos o más miembros en el mismo tipo que solo difieren en el número o tipo de parámetros, pero tienen el mismo nombre. Por ejemplo, en la siguiente tabla, el `WriteLine` método está sobrecargado:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Dado que solo los métodos, constructores y propiedades indizadas pueden tener parámetros, solo los miembros se pueden sobrecargar.  
  
 La sobrecarga es una de las técnicas más importantes para mejorar la facilidad de uso, productividad y mejorar la legibilidad de bibliotecas reutilizables. Sobrecarga en el número de parámetros permite proporcionar versiones más sencillas de métodos y constructores. Sobrecarga en el tipo de parámetro permite usar el mismo nombre de miembro para realizar operaciones idénticas en un conjunto seleccionado de diferentes tipos de miembros.  
  
 **✓ HACER** intenta utilizar nombres de parámetros descriptivos para indicar el valor predeterminado utilizado por las sobrecargas más cortas.  
  
 **X evitar** variar arbitrariamente los nombres de parámetro en las sobrecargas. Si un parámetro de una sobrecarga representa la misma entrada como un parámetro de otra sobrecarga, los parámetros deben tener el mismo nombre.  
  
 **X evitar** incoherente en el orden de los parámetros en sobrecarga los miembros. Parámetros con el mismo nombre deberían aparecer en la misma posición en todas las sobrecargas.  
  
 **✓ HACER** realizar virtual sólo la sobrecarga más larga (si se requiere la extensibilidad). Las sobrecargas más cortas simplemente deben llamar a través de una sobrecarga mayor.  
  
 **X DO NOT** usar `ref` o `out` modificadores para sobrecargar los miembros.  
  
 Algunos lenguajes no pueden resolver llamadas a sobrecargas similar al siguiente. Además, estas sobrecargas normalmente tienen una semántica completamente diferente y probablemente no debería sobrecargas pero dos métodos independientes en su lugar.  
  
 **X DO NOT** tienen sobrecargas con parámetros en la misma posición que él y los tipos similares pero con una semántica diferente.  
  
 **✓ HACER** permitir `null` que se pasarán para los argumentos opcionales.  
  
 **✓ HACER** usar miembro sobrecarga en lugar de definir miembros con argumentos predeterminados.  
  
 Argumentos predeterminados no son compatibles con CLS.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
