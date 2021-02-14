---
description: 'Más información acerca de: Sobrecarga de miembro'
title: Sobrecarga de miembro
ms.date: 10/22/2008
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: d3a545bfec552686e55c9f713d58784497946819
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641959"
---
# <a name="member-overloading"></a>Sobrecarga de miembro

La sobrecarga de miembro implica la creación de dos o más miembros en el mismo tipo que solo difieren en el número o tipo de parámetros, pero tienen el mismo nombre. Por ejemplo, en lo siguiente, el método `WriteLine`, se sobrecarga:

```csharp
public static class Console {
    public void WriteLine();
    public void WriteLine(string value);
    public void WriteLine(bool value);
    ...
}
```

 Dado que solo los métodos, los constructores y las propiedades indizadas pueden tener parámetros, solo esos miembros se pueden sobrecargar.

 La sobrecarga es una de las técnicas más importantes para mejorar la facilidad de uso, la productividad y la legibilidad de las bibliotecas reutilizables. La sobrecarga en el número de parámetros permite proporcionar versiones más sencillas de constructores y métodos. La sobrecarga en el tipo de parámetro permite usar el mismo nombre de miembro para los miembros que realizan operaciones idénticas en un conjunto seleccionado de tipos diferentes.

 ✔️ DEBE intentar usar nombres de parámetro descriptivos para indicar el valor predeterminado usado por las sobrecargas más cortas.

 ❌ EVITE los nombres de parámetro que varían arbitrariamente en las sobrecargas. Si un parámetro de una sobrecarga representa la misma entrada que un parámetro de otra sobrecarga, los parámetros deben tener el mismo nombre.

 ❌ EVITE ser incoherente en el orden de los parámetros en los miembros sobrecargados. Los parámetros con el mismo nombre deben aparecer en la misma posición en todas las sobrecargas.

 ✔️ DEBE convertir en virtual solo la sobrecarga más larga (si se requiere extensibilidad). Las sobrecargas más cortas simplemente deben llamar a través de una sobrecarga más larga.

 ❌ NO utilice los modificadores `ref` o `out` para sobrecargar los miembros.

 Algunos lenguajes no pueden resolver llamadas a sobrecargas como esta. Además, estas sobrecargas suelen tener una semántica completamente diferente y probablemente no deberían ser sobrecargas, sino dos métodos independientes.

 ❌ NO tener sobrecargas con parámetros en la misma posición y tipos similares con semántica diferente.

 ✔️ DEBE permitir que `null` se pase para los argumentos opcionales.

 ✔️ DEBE usar la sobrecarga de miembros en lugar de definir miembros con argumentos predeterminados.

 Los argumentos predeterminados no son conformes a CLS.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](member.md)
- [Instrucciones de diseño de .NET Framework](index.md)
