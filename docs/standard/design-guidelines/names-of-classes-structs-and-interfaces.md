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
ms.openlocfilehash: 96d9904af0106d797c9fc5199bda76da53874451
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709249"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nombres de clases, estructuras e interfaces
Las instrucciones de nomenclatura que se indican a continuación se aplican a la nomenclatura general de tipos.  
  
 **✓ DO** nombre clases y structs con sustantivos o frases con Pascal.  
  
 Esto distingue los nombres de tipo de los métodos, que se denominan con frases verbales.  
  
 **✓ DO** nombres de las interfaces con frases adjetivo o, en ocasiones con sustantivos o sintagmas nominales.  
  
 Los nombres y frases deben usarse con poca frecuencia y pueden indicar que el tipo debe ser una clase abstracta y no una interfaz.  
  
 **X DO NOT** dar a los nombres de clase un prefijo (p. ej., "C").  
  
 **✓ CONSIDER** finalizar los nombres de las clases derivadas con el nombre de la clase base.  
  
 Esto es muy legible y explica claramente la relación. Algunos ejemplos de esto en el código son: `ArgumentOutOfRangeException`, que es un tipo de `Exception`y `SerializableAttribute`, que es un tipo de `Attribute`. Sin embargo, es importante utilizar una resolución razonable para aplicar esta directriz; por ejemplo, la clase `Button` es un tipo de evento `Control`, aunque `Control` no aparece en su nombre.  
  
 **✓ DO** prefijo los nombres de interfaz con la letra I, para indicar que el tipo es una interfaz.  
  
 Por ejemplo, `IComponent` (nombre descriptivo), `ICustomAttributeProvider` (frase) y `IPersistable` (adjetivo) son nombres de interfaz apropiados. Como con otros nombres de tipo, evite las abreviaturas.  
  
 **✓ DO** Asegúrese de que los nombres difieren solo en la "I" prefijo en el nombre de la interfaz cuando se define un par de interfaz de clase: donde la clase es una implementación estándar de la interfaz.  
  
## <a name="names-of-generic-type-parameters"></a>Nombres de parámetros de tipo genérico  
 Los genéricos se agregaron a .NET Framework 2,0. La característica presentó un nuevo tipo de identificador denominado *parámetro de tipo*.  
  
 **✓ DO** el nombre de parámetros de tipo genérico con nombres descriptivos a menos que sea totalmente explicativa un nombre de letra única y un nombre descriptivo no agregue ningún valor.  
  
 **✓ CONSIDER** utilizando `T` como el nombre del parámetro de tipo para los tipos con un parámetro de tipo de letra única.  
  
```csharp  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ DO** prefijo de nombres de parámetros de tipo descriptivos con `T`.  
  
```csharp  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 **✓ CONSIDER** que indica las restricciones de coloca en un parámetro de tipo en el nombre del parámetro.  
  
 Por ejemplo, un parámetro restringido a `ISession` podría llamarse `TSession`.  
  
## <a name="names-of-common-types"></a>Nombres de tipos comunes  
 **✓ DO** siga las directrices descritas en la tabla siguiente al asignar nombres a los tipos derivados de o implementar determinados tipos de .NET Framework.  
  
|Tipo de base|Instrucciones de tipo derivada o de implementación|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ DO** agregar el sufijo "Attribute" a los nombres de clases de atributos personalizados.|  
|`System.Delegate`|**✓ DO** agregar el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.<br /><br /> **✓ DO** agregar el sufijo "Callback" a los nombres de los delegados distintos de los utilizados como controladores de eventos.<br /><br /> **X DO NOT** agregar el sufijo "Delegate" a un delegado.|  
|`System.EventArgs`|**✓ DO** agregar el sufijo "EventArgs".|  
|`System.Enum`|**X DO NOT** derivan de esta clase; use la palabra clave admitida por el lenguaje en su lugar; por ejemplo, en C#, utilice el `enum` palabra clave.<br /><br /> **X DO NOT** agregar el sufijo "Enum" o "Flag".|  
|`System.Exception`|**✓ DO** agregar el sufijo "Exception".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** agregar el sufijo "Diccionario". Tenga en cuenta que `IDictionary` es un tipo específico de colección, pero esta directriz tiene prioridad sobre las instrucciones de colecciones más generales que se indican a continuación.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ DO** agregar el sufijo "Colección".|  
|`System.IO.Stream`|**✓ DO** agregar el sufijo "Stream".|  
|`CodeAccessPermission IPermission`|**✓ DO** agregar el sufijo "Permisos".|  
  
## <a name="naming-enumerations"></a>Enumeración de nomenclatura  
 Los nombres de los tipos de enumeración (también denominados enumeraciones) en general deben seguir las reglas estándar de nomenclatura de tipos (PascalCasing, etc.). Sin embargo, hay instrucciones adicionales que se aplican específicamente a las enumeraciones.  
  
 **✓ DO** utilizar un nombre de tipo singular para una enumeración a menos que sus valores son campos de bits.  
  
 **✓ DO** utilizar un nombre de tipo plural para una enumeración con los campos de bits como valores, también denominados enumeración de marcas.  
  
 **X DO NOT** utilice el sufijo "Enum" en los nombres de tipo de enumeración.  
  
 **X DO NOT** usar "Marca" o sufijos "Indicadores" en la enumeración de nombres de tipo.  
  
 **X DO NOT** utiliza un prefijo en los nombres de valor de enumeración (p. ej., "ad" para las enumeraciones de ADO.), "rtf" para las enumeraciones de texto enriquecido, etcetera.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
