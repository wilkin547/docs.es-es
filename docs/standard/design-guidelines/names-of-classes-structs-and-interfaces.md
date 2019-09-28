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
author: KrzysztofCwalina
ms.openlocfilehash: 2ecd708ccb8eb91270e8ef9c174b8d7e599a2629
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353698"
---
# <a name="names-of-classes-structs-and-interfaces"></a>Nombres de clases, estructuras e interfaces
Las instrucciones de nomenclatura que se indican a continuación se aplican a la nomenclatura general de tipos.  
  
 **✓ DO** nombre clases y structs con sustantivos o frases con Pascal.  
  
 Esto distingue los nombres de tipo de los métodos, que se denominan con frases verbales.  
  
 **✓ DO** nombres de las interfaces con frases adjetivo o, en ocasiones con sustantivos o sintagmas nominales.  
  
 Los nombres y frases deben usarse con poca frecuencia y pueden indicar que el tipo debe ser una clase abstracta y no una interfaz.  
  
 **X DO NOT** dar a los nombres de clase un prefijo (p. ej., "C").  
  
 **✓ CONSIDER** finalizar los nombres de las clases derivadas con el nombre de la clase base.  
  
 Esto es muy legible y explica claramente la relación. Algunos ejemplos de esto en el código son: `ArgumentOutOfRangeException`, que es un tipo de `Exception` y `SerializableAttribute`, que es un tipo de `Attribute`. Sin embargo, es importante utilizar una resolución razonable para aplicar esta directriz; por ejemplo, la clase `Button` es un tipo de evento `Control`, aunque `Control` no aparece en su nombre.  
  
 **✓ DO** prefijo los nombres de interfaz con la letra I, para indicar que el tipo es una interfaz.  
  
 Por ejemplo, `IComponent` (Sustantivo descriptivo), `ICustomAttributeProvider` (frase) y `IPersistable` (adjetivo) son nombres de interfaz apropiados. Como con otros nombres de tipo, evite las abreviaturas.  
  
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
  
|Tipo base|Instrucciones de tipo derivada o de implementación|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ DO** agregar el sufijo "Attribute" a los nombres de clases de atributos personalizados.|  
|`System.Delegate`|**✓ DO** agregar el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.<br /><br /> **✓ DO** agregar el sufijo "Callback" a los nombres de los delegados distintos de los utilizados como controladores de eventos.<br /><br /> **X DO NOT** agregar el sufijo "Delegate" a un delegado.|  
|`System.EventArgs`|**✓ DO** agregar el sufijo "EventArgs".|  
|`System.Enum`|**X DO NOT** derivan de esta clase; use la palabra clave admitida por el lenguaje en su lugar; por ejemplo, en C#, utilice el `enum` palabra clave.<br /><br /> **X DO NOT** agregar el sufijo "Enum" o "Flag".|  
|`System.Exception`|**✓ DO** agregar el sufijo "Exception".|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** agregar el sufijo "Diccionario". Tenga en cuenta que `IDictionary` es un tipo específico de colección, pero esta directriz tiene prioridad sobre la directriz de colecciones más general que se indica a continuación.|  
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
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 @no__t 0Reprinted por el permiso de Pearson Education, Inc. de las directrices de diseño de [Framework: Convenciones, expresiones y patrones para bibliotecas de .NET reutilizables, 2ª edición @ no__t-0 de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 de Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows. *  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
- [Instrucciones de nomenclatura](../../../docs/standard/design-guidelines/naming-guidelines.md)
