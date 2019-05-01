---
title: Sobrecarga de miembro
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: b13f9e1551aec7e53ba1ac2ed0b9049d46b0a756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945552"
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
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
