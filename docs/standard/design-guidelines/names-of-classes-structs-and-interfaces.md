---
title: Nombres de clases, estructuras e interfaces
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401242"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nombres de clases, estructuras e interfaces
Las directrices de nomenclatura siguientes se aplican a la nomenclatura de tipos generales.

 ✔️ DO nombra clases y estructuras con sustantivos o frases de sustantivo, utilizando PascalCasing.

 Esto distingue los nombres de tipo de los métodos, que se nombran con frases verbales.

 ✔️ el nombre DO interactúa con frases adjetivas, o ocasionalmente con sustantivos o frases de sustantivo.

 Los sustantivos y las frases de sustantivos se deben usar raramente y pueden indicar que el tipo debe ser una clase abstracta y no una interfaz.

 ❌NO asigne a los nombres de clase un prefijo (por ejemplo, "C").

 ✔️ CONSIDER termina el nombre de las clases derivadas con el nombre de la clase base.

 Esto es muy legible y explica la relación claramente. Algunos ejemplos de esto `ArgumentOutOfRangeException`en el código `Exception`son: `SerializableAttribute`, que es `Attribute`una especie de , y , que es una especie de . Sin embargo, es importante utilizar un juicio razonable al aplicar esta directriz; por ejemplo, `Button` la clase `Control` es un `Control` tipo de evento, aunque no aparece en su nombre.

 ✔️ nombres de interfaz de prefijo DO con la letra I, para indicar que el tipo es una interfaz.

 Por ejemplo, `IComponent` (nombre `ICustomAttributeProvider` descriptivo), (frase `IPersistable` de sustantivo) y (adjetivo) son nombres de interfaz adecuados. Al igual que con otros nombres de tipo, evite las abreviaturas.

 ✔️ do asegurarse de que los nombres difieren sólo por el prefijo "I" en el nombre de la interfaz cuando se define un par clase-interfaz donde la clase es una implementación estándar de la interfaz.

## <a name="names-of-generic-type-parameters"></a>Nombres de parámetros de tipo genérico
 Los genéricos se agregaron a .NET Framework 2.0. La característica introdujo un nuevo tipo de identificador llamado *parámetro de tipo*.

 ✔️ DO nombra parámetros de tipo genérico con nombres descriptivos a menos que un nombre de una sola letra sea completamente autoexplicativo y un nombre descriptivo no agregaría valor.

 ✔️ considerar `T` como nombre de parámetro de tipo para tipos con un parámetro de tipo de letra única.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ nombres de parámetro `T`de tipo descriptivo de prefijo DO con .

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️ CONSIDERA que indica las restricciones colocadas en un parámetro de tipo en el nombre del parámetro.

 Por ejemplo, un parámetro `ISession` restringido `TSession`a podría llamarse .

## <a name="names-of-common-types"></a>Nombres de tipos comunes
 ✔️ siguen las instrucciones que se describen en la tabla siguiente al asignar nombres a los tipos derivados o implementar determinados tipos de .NET Framework.

|Tipo base|Guía de tipos derivados/de implementación|
|---------------|------------------------------------------|
|`System.Attribute`|✔️ , agregue el sufijo "Attribute" a los nombres de las clases de atributo personalizadas.|
|`System.Delegate`|✔️ DO agregue el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.<br /><br /> ✔️ , agregue el sufijo "Callback" a los nombres de delegados distintos de los utilizados como controladores de eventos.<br /><br /> ❌NO agregue el sufijo "Delegate" a un delegado.|
|`System.EventArgs`|✔️ , agregue el sufijo "EventArgs."|
|`System.Enum`|❌NO derive de esta clase; utilizar la palabra clave admitida por su idioma en su lugar; por ejemplo, en C-, utilice la `enum` palabra clave.<br /><br /> ❌NO agregue el sufijo "Enum" o "Flag."|
|`System.Exception`|✔️ no agregue el sufijo "Exception."|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️ no agregue el sufijo "Dictionary." Tenga `IDictionary` en cuenta que es un tipo específico de colección, pero esta directriz tiene prioridad sobre la directriz de colecciones más general que sigue.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️, agregue el sufijo "Collection."|
|`System.IO.Stream`|✔️ , agregue el sufijo "Stream."|
|`CodeAccessPermission IPermission`|✔️ no agregue el sufijo "Permiso."|

## <a name="naming-enumerations"></a>Nombrar enumeraciones
 Los nombres de los tipos de enumeración (también denominados enumeraciones) en general deben seguir las reglas de nomenclatura de tipos estándar (PascalCasing, etc.). Sin embargo, hay directrices adicionales que se aplican específicamente a las enumeraciones.

 ✔️ DO usan un nombre de tipo singular para una enumeración a menos que sus valores sean campos de bits.

 ✔️ DO usa un nombre de tipo plural para una enumeración con campos de bits como valores, también denominados flags enum.

 ❌NO utilice un sufijo "Enum" en los nombres de tipo enum.

 ❌NO utilice sufijos "Flag" o "Flags" en los nombres de tipo enum.

 ❌NO utilice un prefijo en los nombres de valores de enumeración (por ejemplo, "ad" para enumeraciones de ADO, "rtf" para enumeraciones de texto enriquecido, etc.).

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
