---
title: Sobrecarga de miembro
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2127497d294cbfd4e1bb24d033f432378627ff13
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45619066"
---
# <a name="member-overloading"></a>Sobrecarga de miembro
Sobrecarga de miembro significa crear dos o más miembros en el mismo tipo que solo difieren en el número o tipo de parámetros, pero tienen el mismo nombre. Por ejemplo, en la siguiente, el `WriteLine` método está sobrecargado:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Dado que solo los métodos, constructores y propiedades indizadas pueden tener parámetros, solo los miembros se pueden sobrecargar.  
  
 La sobrecarga es una de las técnicas más importantes para mejorar la facilidad de uso, la productividad y mejorar la legibilidad de bibliotecas reutilizables. La sobrecarga en el número de parámetros hace posible proporcionar versiones más sencillas de métodos y constructores. La sobrecarga en el tipo de parámetro permite usar el mismo nombre de miembro para realizar operaciones idénticas en un conjunto seleccionado de diferentes tipos de miembros.  
  
 **✓ DO** intenta utilizar nombres de parámetros descriptivos para indicar el valor predeterminado utilizado por las sobrecargas más cortas.  
  
 **X AVOID** variar arbitrariamente los nombres de parámetro en las sobrecargas. Si un parámetro de una sobrecarga representa la misma entrada como un parámetro en la otra sobrecarga, los parámetros deben tener el mismo nombre.  
  
 **X AVOID** incoherente en el orden de los parámetros en sobrecarga los miembros. Parámetros con el mismo nombre deberían aparecer en la misma posición en todas las sobrecargas.  
  
 **✓ DO** realizar virtual sólo la sobrecarga más larga (si se requiere la extensibilidad). Las sobrecargas más cortas simplemente deben llamar a través de una sobrecarga mayor.  
  
 **X DO NOT** usar `ref` o `out` modificadores para sobrecargar los miembros.  
  
 Algunos lenguajes no pueden resolver llamadas a sobrecargas similar al siguiente. Además, estas sobrecargas normalmente tienen una semántica completamente diferente y no deben ser las sobrecargas, pero dos métodos independientes en su lugar.  
  
 **X DO NOT** tienen sobrecargas con parámetros en la misma posición que él y los tipos similares pero con una semántica diferente.  
  
 **✓ DO** permitir `null` que se pasarán para los argumentos opcionales.  
  
 **✓ DO** usar miembro sobrecarga en lugar de definir miembros con argumentos predeterminados.  
  
 Argumentos predeterminados no son conformes a CLS.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
