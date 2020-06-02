---
title: Nombres de clases, estructuras e interfaces
description: Siga estas instrucciones para asignar nombres a clases, Structs e interfaces como parte de las instrucciones para diseñar bibliotecas que extienden e interactúan con las bibliotecas de .NET.
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
ms.openlocfilehash: b9de9329cc8e1bfc47a46523c7119bb3b2c244d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290219"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nombres de clases, estructuras e interfaces
Las instrucciones de nomenclatura que se indican a continuación se aplican a la nomenclatura general de tipos.

 ✔️ los nombres de las clases y los Structs con sustantivos o sintagmas nominales, mediante PascalCasing.

 Esto distingue los nombres de tipo de los métodos, que se denominan con frases verbales.

 ✔️ las interfaces de nombre con frases adjetivales, o ocasionalmente, con sustantivos o sintagmas nominales.

 Los nombres y frases deben usarse con poca frecuencia y pueden indicar que el tipo debe ser una clase abstracta y no una interfaz.

 ❌NO proporcione a los nombres de clase un prefijo (por ejemplo, "C").

 ✔️ considere la posibilidad de terminar el nombre de las clases derivadas con el nombre de la clase base.

 Esto es muy legible y explica claramente la relación. Algunos ejemplos de esto en el código son: `ArgumentOutOfRangeException` , que es un tipo de `Exception` , y `SerializableAttribute` , que es un tipo de `Attribute` . Sin embargo, es importante utilizar una resolución razonable para aplicar esta directriz; por ejemplo, la `Button` clase es un tipo de `Control` evento, aunque `Control` no aparece en su nombre.

 ✔️ Prefije los nombres de interfaz con la letra I, para indicar que el tipo es una interfaz.

 Por ejemplo, `IComponent` (nombre descriptivo), `ICustomAttributeProvider` (frase) y `IPersistable` (adjetivo) son nombres de interfaz apropiados. Como con otros nombres de tipo, evite las abreviaturas.

 ✔️ asegurarse de que los nombres solo difieren en el prefijo "I" del nombre de la interfaz cuando se define un par clase-interfaz, donde la clase es una implementación estándar de la interfaz.

## <a name="names-of-generic-type-parameters"></a>Nombres de parámetros de tipo genérico
 Los genéricos se agregaron a .NET Framework 2,0. La característica presentó un nuevo tipo de identificador denominado *parámetro de tipo*.

 ✔️ los parámetros de tipo genérico de nombre con nombres descriptivos a menos que un nombre de una sola letra sea completamente descriptivo y un nombre descriptivo no agregue ningún valor.

 ✔️ CONSIDERE `T` la posibilidad de usar como nombre de parámetro de tipo para los tipos con un parámetro de tipo de una sola letra.

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 ✔️ HACER prefijos para los nombres de parámetro de tipo descriptivo con `T` .

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 ✔️ considere la posibilidad de indicar restricciones colocadas en un parámetro de tipo en el nombre del parámetro.

 Por ejemplo, se podría llamar a un parámetro restringido a `ISession` `TSession` .

## <a name="names-of-common-types"></a>Nombres de tipos comunes
 ✔️ Siga las instrucciones que se describen en la tabla siguiente al asignar nombres a tipos derivados de o implementar determinados tipos de .NET Framework.

|Tipo base|Instrucciones de tipo derivada o de implementación|
|---------------|------------------------------------------|
|`System.Attribute`|✔️ Agregue el sufijo "Attribute" a los nombres de las clases de atributos personalizados.|
|`System.Delegate`|✔️ Agregue el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.<br /><br /> ✔️ Agregue el sufijo "callback" a los nombres de los delegados distintos de los que se usan como controladores de eventos.<br /><br /> ❌NO agregue el sufijo "Delegate" a un delegado.|
|`System.EventArgs`|✔️ Agregue el sufijo "EventArgs".|
|`System.Enum`|❌NO derive de esta clase; Use en su lugar la palabra clave compatible con el lenguaje; por ejemplo, en C#, use la `enum` palabra clave.<br /><br /> ❌NO agregue el sufijo "enum" o "flag".|
|`System.Exception`|✔️ Agregue el sufijo "Exception".|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|✔️ Agregue el sufijo "Dictionary". Tenga en cuenta que `IDictionary` es un tipo específico de colección, pero esta directriz tiene prioridad sobre las instrucciones de colecciones más generales que se indican a continuación.|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|✔️ agregar el sufijo "Collection".|
|`System.IO.Stream`|✔️ agregar el sufijo "Stream".|
|`CodeAccessPermission IPermission`|✔️ agregar el sufijo "Permission".|

## <a name="naming-enumerations"></a>Enumeración de nomenclatura
 Los nombres de los tipos de enumeración (también denominados enumeraciones) en general deben seguir las reglas estándar de nomenclatura de tipos (PascalCasing, etc.). Sin embargo, hay instrucciones adicionales que se aplican específicamente a las enumeraciones.

 ✔️ usar un nombre de tipo singular para una enumeración a menos que sus valores sean campos de bits.

 ✔️ usar un nombre de tipo plural para una enumeración con campos de bits como valores, también denominados enumeración Flags.

 ❌No use un sufijo "enum" en los nombres de tipo enum.

 ❌No utilice los sufijos "flag" o "flags" en los nombres de tipo enum.

 ❌No use un prefijo en los nombres de los valores de enumeración (por ejemplo, "ad" en las enumeraciones de ADO, "rtf" para las enumeraciones de texto enriquecido, etc.).

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Directrices de diseño de marco](index.md)
- [Instrucciones de nomenclatura](naming-guidelines.md)
